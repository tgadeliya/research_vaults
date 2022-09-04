Model card

- Joint training of retrieval and re-ranker
- Data augmentation strategy for proposed training
- 



This mode tries to solve problem of joint training retrieval and reranker

Typically, this is two different model, trained differently, because they should optimize different objective. Retrieval tries to optimize probability of positive passage comparing to negative, re-ranker usually learned in pointwise or pairwise manner

In this work, authors propose joint training of this two models. Thye adopt listwise traiing approach for both retriever nad re-ranker, where the relevance socre are computed according to a list of positive and negative passages.




Dynamic listwise distillation
- Re-ranker adopts more capable cross-encoder architecture
We calculate normalized scores for Query and Passage Set for retrieval and re-ranker. After we use combination of the next objectives:
- KL-divergence between retrieval's dual-encoders and re-ranker cross-encoders
- CE between re-ranker list and golden labels


To perform such training we should generate candidate passage list P_q for every query. It is important to have diverse and high-quality candidate passages, which may better represent the distribution of all passages in the whole collection.
Prior works solving this in different ways:
- DPR and ANCE use randomly sampled hard negatives or BM25 + in-batch negatives
- RocketQA (first version) encorporates




Experiments:
- Datasets: MS Marco, NQ
- As they evaluate only retrieval component, MRR(Mean reciprocal Rank) and Recall@k is used

Retrieval results
- Comparing PAIR and RocketQAv2. They have similar performance. Analysing deeper, authors mention, that on most restrict metrics (MRR@10 and R@5) their approach seems to be better. They connect that with distillation between re-ranker and retriever. Morover, RQA2 trained only on in-domain data, but PAIR used out-domain data for pre-trainig
- While comparing RQAv2 with DPR, we can notice difference in backbone model. To eliminate this effect and compare only approaches to retrieval training they train DPR-E - DPR with Ernie backbone. From my point of view, discrepancy stays in re-ranker, which actually adding more parameters during training, which we tries to evenly distill between models (evenly?).

Re-ranker results
- Comparing RocketQA and RQA2 inserted into RocketQA pipeline, we see improvement

