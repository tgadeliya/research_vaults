### Introduction

There are multiple approaches to store knowledge used for solving tasks (QA especially). New papers shows that large autoregressive models can contain knowledge learned from training data and encoded in parameters (Roberts paper). But we don't have access to this knowledge, hence we can't edit or explicitly add some knowledge. Another problem can be halucinasion during generation of the answer.
From the other side, we have non-parametric knowledge storage - DPR or REALM models. This approach allows easily modify this knowledge or have more interpretable answering process, e.g. DPR retriever returns documents which stands base for future answer. 
This work tries to combine two approaches by using hybrid parametric and non-parametric memory with seq2seq models.


### Model

Modified Retriver-Reader approach with second stage Generator that can be trained end-to-end.

##### Retriever
This component based on DPR model approach, so main purpose to retrieve top-k documents given encoded question and set of documents. For encoding pretrained DPR models: BERT-base document and BERT-base query encoder used. After encoding this problem reduced to Maximum Inner Product Search solved with FAISS.

More formally, we choose top-k documents $z$ for question $x$ based on similarity  $p_\eta$ , which calculated  
$$
\begin{align*}
p_{\eta}(z|x) \propto exp ( \textbf{d}(z)^\top \textbf{q}(x)^\top)\newline
\textbf{d}(z) = BERT_d(z)\newline
\textbf{q}(x) = BERT_q(x)&&\newline
\end{align*}
$$

#### Generator
This component can be modeled using encoder-decoder models. Be default pre-trained BART-large is used.
Retrieved documents are concatenated with encoded question to prepare input for Generator (how precisely it is done?)

Variations:
To achieve end-to-end training, documents seems as latent variables, which allow to use them during generation. Hence, two models  presented by authors: 

RAG-sequence - generate answer tokens based on single document. After generating output for each document, which are then marginalized.

$$
p_{\text {RAG-Sequence }}(y \mid x) \approx \sum_{z \in \text { top- } k(p(\cdot \mid x))} p_{\eta}(z \mid x) p_{\theta}(y \mid x, z)=\sum_{z \in \text { top- } k(p(\cdot \mid x))} p_{\eta}(z \mid x) \prod_{i}^{N} p_{\theta}\left(y_{i} \mid x, z, y_{1: i-1}\right)
$$

RAG-token - every answer token can be generated based on different retrieved document 

$$
p_{\text {RAG-Token }}(y \mid x) \approx \prod_{i}^{N} \sum_{z \in \text { top- } k(p(\cdot \mid x))} p_{\eta}(z \mid x) p_{\theta}\left(y_{i} \mid x, z, y_{1: i-1}\right)
$$




**Training**

Training performed end-to-end without direct supervision on what document should be retrieved. Moreover, in Retriever we fine-tune only question encoder and freeze document encoder to avoid whole document index base recalculation. 

**Decoding**

TODO: kind of difficult process


**Experiments**

Using document encoder to encode Wikipedia dump + FAISS + Hierarchical Navigable Small World approximation

This more is very universal and can perform different types of tasks:
- ODQA - classic scenario with external knowledge encoded (Wikipedia dump)
- Closed-book QA - using only parametric knowledge to answer the question
- Abstractive QA -  MSMARCO dataset : "The task consists of questions, ten gold passages retrieved from a search engine for each question, and a full sentence answer annotated from the retrieved passages". RAG doesn't use passages, only question-answer pairs" 


Analysis

- Generation better than retrieval, because documents without explicit answer, but relevant information will usefull to the model.
- "Furthermore, RAG can generate correct answers even when the correct answer is not in any retrieved document, achieving 11.8% accuracy in such cases for NQ, where an extractive model would score 0%." - but it is not so much
- More diverse generation of text without no additional diversity-promoting decoding (but it use beam decoding as default in RAG-sequence mode ??) 
- Trainable Retriever can improve results comparing to BM25 and frozen pre-trained DPR retriever
-  They use Wiki dump from 2016 and 2018 to evaluate whether simple data replacement for retriever will help. Experiments shows, that it works. 
- Ablations shows that increasing number of retrieved documents shows small imrpovements, but not enough to suggesting switch to top-k' >> top-k









