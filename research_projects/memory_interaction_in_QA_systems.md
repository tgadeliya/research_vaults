
## Research report 0:

This main aim of this work to research how parametric and non-parametric memory interact through extracting properties on examples

Hypothesis:
- While parametric and non-parametric memory contains conterfactual facts, model rely on parametric memory
- We can control extent of model usage of parametric and non-parametric memory
- Contrfactual facts in parametric and non-parametric memory influence model confidence on tasks


Idea:
- Whether model memorize facts from retriever during training
- Test pre-traiined on QA task and without models, to see what changes during training. 
- Think about geographic aspect and time. Which memory more influenced by this aspects
- Use change in probability as measure of model confidence
- We can develop method to make model rely on parametric or non-parametric memory
- Research on encoder and decoder memory of BART
- Use FiD and RAG models
- Search datasets with contfactual QA





## Research report 1:
- Research on similar papers
- Research on methods of how to do main things: method to check memory, data to experiment, metrics to evaluation




### [Entity-Based Knowledge Conflicts in Question Answering](http://arxiv.org/abs/2202.05262)
- This actually the same idea that I have. They desided to check how parametric and non-parametric memory is working together.

- Reference: [Hurdles to Progress in Long-form Question Answering](http://arxiv.org/abs/2202.05262)
	- Create SOTA model to answer long-form QA on ELI5 dataset. Performed analysis, that showed some properties
	- (c) Conditioning answer generation on random documents instead of relevant ones does not measurably impact its factual correctness.
	- ![[Pasted image 20230104123423.png|250x200]]
	- Retrieval has small influence of metrics for system from paper.
	- Moreover, other systems have the same problems on this task (BART, RAG,etc.)
	- But this may be important for LFQA, not for factual QA

- Their objective is to understand how systems with parametric and non-parametric knowledge works using conflicting 
situations - when contextual knowledge contradicts with knowledge learned during pre-training or fine-tuning.
- #### **Because the space of knowledge conflicts is broad, we restrict ourselves to the space of entity-based conflicts – restricted to named entity substitutions.**
	- ##### ! This is important, because can give more space for research with other approaches

Intro Results:
- Model over-relied on parametric knowledge. Factors that inflence that influence such behaviour: model size, model type, quality of retrieval during training, domain similarity and specific characteristics of answers

Experiment:
- DATA: They substitute NE in NQ and NewsWA to get question that conflicts with parametric memory.
	- they substitute NE in answer and all mention of NE in the golden retrieved documents.
	- NOTE: It is potentially problematic to choose good way to substitute NE. E.g. theoretically, when changing geographical NE to personality NE it creates disambiguity between document and NE and confuse model on semantic level 
	- NOTE: in paper "....We provide tools to identify coherence-preserving substitutions and create substitutions with certain characteristics..."
	- five entity types that are well represented in question answering datasets: person (PER), date (DAT), numeric (NUM), organization (ORG), and location (LOC).
	- Substitution policy types:
		- Corpus Substitution - replace NE with other NE from the same dataset (in-domain) randomly sampled through gold answers and have the same entity type
		- Type Swap Substitution - replace NE with other NE with different type
		- Popularity substitution - same as CS, but additional condition that new NE should be popular among Wikidata users
		- Alias substitution - replace NE with semantically equal paraphrase from Wikidata
	- ![[Pasted image 20230104135318.png|300x150]] - quality of substitution

### New ideas
- Experiment: Whether generative model + index are robust to changes in time after FT То есть если мы файтюним то по умолчанию генеративная модель будет выбирать более правильные ответы. Можно проверить MLM как средство получения таких знаний
- use as retrieved documents the same document but from different time. This way we provide conflict for this

