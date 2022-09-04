### T2: Self-supervised Representation Learning for Speech Processing
[Live Session Recording](https://us06web.zoom.us/rec/play/6BdZPZbtIbNmotX8VZHZl34LDzfTkjgAcNlaDdClw5-4k2f8thrUeE-l-CvU_Nn8o2mGXnIPXmmrPq0s.QVCnuE5VXPM9iq9H?autoplay=true&startTime=1657464317000)

[Self-Supervised Speech Representation Learning: A Review](https://arxiv.org/abs/2205.10643) - paper version of this tutorial
[McGurk effect](https://en.wikipedia.org/wiki/McGurk_effect) - speech perception is multimodal
[NeurIPS 2021 competition on evaluation of audio representations](https://nips.cc/Conferences/2021/ScheduleMultitrack?event=21982)

### T6: Contrastive Data and Learning for Natural Language Processing
[Live Session Recording](https://zoom.us/rec/play/KtvYvwUYB8Vl5VfmGZiuf_GnS538AwOKouyaljzoxdtkVRx-pe9i6-bupD9mot1AYR-U9WwEWMe-HfpZ.47n5ptMNPEWqnolI?autoplay=true&startTime=1657484780000)

[Curated list of papers on Contrastive Learning Theme](https://github.com/ryanzhumich/Contrastive-Learning-NLP-Papers)


Stack for contrastive text classification training
- [CERT: Contrastive Self-supervised Learning for Language Understanding](https://arxiv.org/abs/2005.12766)
- [Cutoff augmentation](https://arxiv.org/abs/2009.13818)
- [Momentum Contrast for Unsupervised Visual Representation Learning](https://arxiv.org/pdf/1911.05722.pdf)
- [Not All Negatives are Equal: Label-Aware Contrastive Loss for Fine-grained Text Classification]() 


QA papers:
- [xMoCo: Cross Momentum Contrastive Learning for Open-Domain Question Answering](https://aclanthology.org/2021.acl-long.477.pdf)
- [Approximate Nearest Neighbor Negative Contrastive Learning for Dense Text Retrieval](https://openreview.net/forum?id=zeFrfgyZln) - negatives got from retrieved documents. Trained similar to REALM async index refresh
- [Contrastive Domain Adaptation for Question Answering using Limited Text Corpora](https://aclanthology.org/2021.emnlp-main.754.pdf) - qa model + question generation model 


NER papers:
- [CONTaiNER: Few-Shot Named Entity Recognition via Contrastive Learning](https://arxiv.org/abs/2109.07589)




## Session1
- [Meta Learning for Natural Language Processing: A Survey](https://aclanthology.org/2022.naacl-main.49.pdf) - good source of models and approaches. There is a tutorial (ACL2022?) based on this paper

(ref) [Transformer Feed-Forward Layers Are Key-Value Memories](https://aclanthology.org/2021.emnlp-main.446.pdf)

[Multi2WOZ: A Robust Multilingual Dataset and Conversational Pretraining for Task-Oriented Dialog](https://aclanthology.org/2022.naacl-main.270.pdf) 
	- TOD-XLMR - Multilingual model for TOD
	- [TOD-BERT: Pre-trained Natural Language Understanding for Task-Oriented Dialogue](https://aclanthology.org/2020.emnlp-main.66.pdf) - BERT-like trained in contrastive fashion to understand TOD dialogue.


Contrastive explanation:
- **Text annotation idea**: Annotate classification as NER task. This will add more explainability
- http://contrxt.ai/

[A Rationale-Centric Framework for Human-in-the-loop Machine Learning](https://aclanthology.org/2022.acl-long.481.pdf)


**Idea**: Use re-weighting for InfoNCE loss based on metadata - tags, intents

## Session2
- [ElitePLM: An Empirical Study on General Language Ability Evaluation of Pretrained Language Models](https://aclanthology.org/2022.naacl-main.258.pdf)
- [DUCK: Rumour Detection on Social Media by Modelling User and Comment Propagation Networks](https://aclanthology.org/2022.naacl-main.364.pdf)- Analyse structure of the comments.
- [Early Rumor Detection Using Neural Hawkes Process with a New Benchmark Dataset](https://aclanthology.org/2022.naacl-main.302)
	- Idea: Model with built-in data and predict based on news on Wikipedia. Knowledge-augmented
	- Rumor detection as fact-checking
	- Learn more about Hawkes process
- [Improving Compositional Generalization with Latent Structure and Data Augmentation](https://aclanthology.org/2022.naacl-main.323)
- [KCD: Knowledge Walks and Textual Cues Enhanced Political Perspective Detection in News Media](https://aclanthology.org/2022.naacl-main.304.pdf)
	- use for CHGK. Create dataset based on that
	- Open AI idea with RL elarning. Create bot that learn with itself.
	- Question section: this methods don't generalize, instead searching shortcuts. Be aware of that. 
- [DiffCSE: Difference-based Contrastive Learning for Sentence Embeddings](https://aclanthology.org/2022.naacl-main.311)
	- [Equivariant Contrastive Learning](https://arxiv.org/abs/2111.00899)
	- Read this paper

## Session3
- [Fact Checking with Insufficient Evidence](https://aclanthology.org/2022.tacl-1.43)
- [Adaptable Adapters](https://aclanthology.org/2022.naacl-main.274.pdf)

## Session4
- [Measure and Improve Robustness in NLP Models: A Survey](https://aclanthology.org/2022.naacl-main.339/
- [Boosted Dense Retriever](https://aclanthology.org/2022.naacl-main.226/)
	- check PAQ paper
	- a lot of useful references
	- COMET model
- [GPL: Generative Pseudo Labeling for Unsupervised Domain Adaptation of Dense Retrieval](https://aclanthology.org/2022.naacl-main.168/)
- [ColBERTv2: Effective and Efficient Retrieval via Lightweight Late Interaction](https://aclanthology.org/2022.naacl-main.272/)
- [Necessity and Sufficiency for Explaining Text Classifiers: A Case Study in Hate Speech Detection](https://aclanthology.org/2022.naacl-main.192/)


## Session5
- [Explaining Why: How Instructions and User Interfaces Impact Annotator Rationales When Labeling Text Data](https://aclanthology.org/2022.naacl-main.38/)
- [Deconstructing NLG Evaluation: Evaluation Practices, Assumptions, and Their Implications](https://aclanthology.org/2022.naacl-main.24) - paper based on interview of ML people about NLG (say what?)

## Session6
- [Quantifying Adaptability in Pre-trained Language Models with 500 Tasks](https://aclanthology.org/2022.naacl-main.346/)
- [A Balanced Data Approach for Evaluating Cross-Lingual Transfer: Mapping the Linguistic Blood Bank](https://aclanthology.org/2022.naacl-main.361/)
- [On the Economics of Multilingual Few-shot Learning: Modeling the Cost-Performance Trade-offs of Machine Translated and Manual Data](https://aclanthology.org/2022.naacl-main.98/)
- [Lifting the Curse of Multilinguality by Pre-training Modular Transformers](https://aclanthology.org/2022.naacl-main.255/)
- [When is BERT Multilingual? Isolating Crucial Ingredients for Cross-lingual Transfer](https://aclanthology.org/2022.naacl-main.264/)
- [Combating the Curse of Multilinguality in Cross-Lingual WSD by Aligning Sparse Contextualized Word Representations](https://aclanthology.org/2022.naacl-main.176/)


## Session7
- [WECHSEL: Effective initialization of subword embeddings for cross-lingual transfer of monolingual language models](https://aclanthology.org/2022.naacl-main.293/)
- [LaMemo: Language Modeling with Look-Ahead Memory](https://aclanthology.org/2022.naacl-main.422/)
- [What do Toothbrushes do in the Kitchen? How Transformers Think our World is Structured](https://aclanthology.org/2022.naacl-main.425/)
- [Two Contrasting Data Annotation Paradigms for Subjective NLP Tasks](https://aclanthology.org/2022.naacl-main.13/)


## Session9
- [ConfliBERT: A Pre-trained Language Model for Political Conflict and Violence](https://aclanthology.org/2022.naacl-main.400/)


## Session10
- [Evidentiality-guided Generation for Knowledge-Intensive NLP Tasks](https://aclanthology.org/2022.naacl-main.162/)
- [Learning to Retrieve Passages without Supervision](https://aclanthology.org/2022.naacl-main.193/)


## Workshops
- [Deep Learning for Low-Resource NLP](https://sites.google.com/view/deeplo-2022/home)
	- Check papers list:
- [Workshop on Multilingual Information Access (MIA)](https://mia-workshop.github.io/)
