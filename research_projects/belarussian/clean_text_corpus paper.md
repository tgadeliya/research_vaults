Paper plan:
- Review of existing resources for Belarussian
- Preparing new data: corpuses, parallel text, ?
- experiments with existing models 



# Review of existing resources for Belarussian
- Check for additional data from paper Web Quality at glance
- OSCAR
- mC4
- WikiMatrix [[34]](https://ruder.io/state-of-multilingual-ai/index.html#fn34) 
- CCAligned [[35]](https://ruder.io/state-of-multilingual-ai/index.html#fn35)

Models from pic
![[Pasted image 20221129115156.png|400x200]]

# Experiments with existing models

Models:
- mBERT
- BLOOM (?)
- XLM-R
- mDeBERTa
- VECO
- CoFe
- T-URlv2/5
- STILTs
- FILTER
- HiCTL
- ERNIE-M
- Polyglot
- InfoXLM
- XLM-E (weights?)



Whisper [[55]](https://ruder.io/state-of-multilingual-ai/index.html#fn55) and PaLI [[56]](https://ruder.io/state-of-multilingual-ai/index.html#fn56), which are pre-trained on large amounts of weakly supervised data from the web for ASR and image captioning in 96 and 109 languages respectively



Similar models:
- AfriBERTa [[80]](https://ruder.io/state-of-multilingual-ai/index.html#fn80), AfroXLM-R [[81]](https://ruder.io/state-of-multilingual-ai/index.html#fn81), and KinyaBERT [[82]](https://ruder.io/state-of-multilingual-ai/index.html#fn82) and models for Indonesian languages such as IndoBERT [[71:1]](https://ruder.io/state-of-multilingual-ai/index.html#fn71)[[72:1]](https://ruder.io/state-of-multilingual-ai/index.html#fn72) and IndoGPT [[73:1]](https://ruder.io/state-of-multilingual-ai/index.html#fn73). For Indian languages, there are text-based models such as IndicBERT [[74:1]](https://ruder.io/state-of-multilingual-ai/index.html#fn74) and MuRIL [[83]](https://ruder.io/state-of-multilingual-ai/index.html#fn83) and speech models such as CLSRIL [[84]](https://ruder.io/state-of-multilingual-ai/index.html#fn84) and IndicWav2Vec [[85]](https://ruder.io/state-of-multilingual-ai/index.html#fn85). Many of these approaches train a model on several related languages and are thus able to leverage positive transfer and to be much more efficient than larger multilingual models. See [[86]](https://ruder.io/state-of-multilingual-ai/index.html#fn86) and [[87]](https://ruder.io/state-of-multilingual-ai/index.html#fn87) for recent surveys of recent multilingual models in NLP and speech.



NeurIPS:
- https://datasets-benchmarks-proceedings.neurips.cc/paper/2021