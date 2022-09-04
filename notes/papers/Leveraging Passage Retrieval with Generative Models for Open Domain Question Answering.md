This model continue to investigate combining parametric and non-parametric knowledge sources, started in RAG and REALM. 
Authors propose simple architecture, two-stage approach: Retriever and Reader.
As Reader they use BM25 and DPR model, so there is nothing new. Main novelty of this paper and what differs it from RAG is encoder-decoder reader. More conretely, lets look to reader encoder and decoder separately:

**reader encoder** 

To prepare input for encoder, we should concatenare question with every passage with additional tokens. 
This will have a form 
"question: Q title: T context: P_i ", where Q, T, P_i (i-th passage) should be changes to corresponding text.

After that every string processed indepedently with encoder and result concatenated in one vector. This is our encoder output that will be used in decoder

**reader decoder**
At this step, for the first time information from different passages combined, using attention and that operation gave name to the model Fusion-in-Decoder.
This approach allow to increase number of passages with linear increase of complexity (instead of quadratical). Moreover, processing encoded passages jointly in  the decoder creates effective mechanism to aggregate (ablation needed) evidences from multiple passages 


**Training details**
- T5 as reader
- 100 passages truncated to 250 words
- DPR passages for NQ, TriviaQA, BM25 for SQuAD
- Answers generated using greedy decoding



**Experiments**
![[Pasted image 20220610122507.png]]
![[Pasted image 20220610123617.png]]

- Authors perform multiple experiments with number of passages 
	- scaling N during development shows increase in performance >> seq2seq are good at combining informations from multiple passages
	- training with smaller N leads to performance degradation >> obvious, but authors propose fine-tuning for 1000 steps with 100 passages which should help