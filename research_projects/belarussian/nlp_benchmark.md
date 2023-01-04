
Initial structure:
	- Existing datasets
		- UD dataset
	- New datasets
		- NER
	- Translated datasets and reviewed
		-...

TODO:
- Paper
- Papers on NER
- Literature review on follow topics: automatic dataset creation (from Wiki), Becnhamrks (for low-resource)
- Plan top-down benchmark




# Testing existing multilingual models and language models for Belarussian
- Models
	- [mBERT](https://github.com/google-research/bert/blob/master/multilingual.md), RemBERT [[16]](https://ruder.io/state-of-multilingual-ai/index.html#fn16), XLM-RoBERTa [[17]](https://ruder.io/state-of-multilingual-ai/index.html#fn17), mBART [[18]](https://ruder.io/state-of-multilingual-ai/index.html#fn18), mT5 [[19]](https://ruder.io/state-of-multilingual-ai/index.html#fn19), and mDeBERTa
	- HF hub models
- Tests on existing data
	- WikiANN prepared
	- Perplexity on test set
	- tokenizers
		- fertility
	- UD task train
		- linear probing
		- FT