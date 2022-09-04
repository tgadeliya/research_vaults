**Introduction**

This paper continue research venue introduced by [[REALM_ Retrieval-Augmented Language Model Pre-Training]] and [[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks]] (or RAG for short). The main novelties are reranker placed between retriever and generator and advanced training procedures.

![[Pasted image 20220614070554.png]]

**Methods**


**Retriever**
They use neural encoders approach from [[Dense Passage Retrieval for Open-Domain Question Answering]] (or DPR for short) and BM25 as the second index. There is no need to manually choose how much examples from different indexes will be used, just passing retrieved examples in reranker. 

**Reranker**
The main utilities come from reranker:
- Can be used to rank multiple retrieval outputs, when their internal scores aren't comparable. E.g. inner product of neural encoders and BM25 index.
- Improve initial retrieval results: retrieve N and choose k << N after ranking.

Reranker based on sequence-pair classification from  paper Noguiera and Cho (2019).

![[Pasted image 20220614072708.png]]

Reranker is a BERT-small model applied to query and passage simultaneously. This contrasts with the retrieval approach, when we use two different models to encode passage and question, because we have huge passage database and it is impossible to run through every passage in every forward pass. This gives us scalability. Using interaction between question and passage will keep high accuracy


For more details on Generator, refer to [[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks]]


**Training**

Due to usage of multiple different components inside the model, there are four training phases:
- DPR training (question, answer, context(provenance))
	- Stage 1 is the same as original training
	- Stage 2 retrieved passages are indexed with HNSW using FAISS 
- Generation training (question, answer, context(provenance))
	- Training is the same as RAG paper
- Reranking training (question, answer)
	- Training performed in isolation using results of DPR and BM25 on training set
	- $loss = - \sum_{i \in Prov} log(softmax(z_r)_i)\text{, where } z_r \text{is a logit from reranker}$
 - End2End training (question, answer)
	 - Difficult, because if reranker scores used during generation instead of DPR scores, DPR encoder won't get gradient. Without through inner product between query encoding and passage encoding.
	 - Authors propose 3 solutions:
		 - Combine DPR and reranker scores - This solition isn't worked, theoretically and in practice. The reason is that DPR scores becomes complementary to reranker.
			 - In text : "gives the highest scores to the passages the reranker is most likely to underrate" Why underrate? Подумав может потому что если реранкер хорошо уверен то сигнал и так хороший А если реранкер не уверен то DPR может выровнять скор
		 - Freeze the query encoder 
			 - This works good enough, best results for WoW. More probably, this is because of earlier training stages, when DPR was trained.
		 - Online Knowledge Distillation

**Inference**
1. Encode using DPR and index with HNSW. => top-12 most similar passages returned.
2. Query used to perform search over index using BM25 (Anserini) => top-12 most similar passages returned.
3. Concat results from DPR and BM-25 and pass into reranker => top-5 passages will be used in generator
4. Top-5 reranker passages are merged with query  and passed to Generator(BART-Large) => 5 output sequences generated.
5. Output sequences weighted over reranker scores => final output