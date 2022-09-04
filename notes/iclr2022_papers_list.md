#### [Comparing Distributions by Measuring Differences that Affect Decision Making](https://openreview.net/forum?id=KB5onONJIAU):
What:
- New approach to measure discrepancy between distributions by calculating optimal loss for specific decision task
- Existing approaches: f-measure, IPM overlaps and extended by novel approach H-Divergence

Why to read:
-  new model for loss function analysis
-  learn about relevant algorithms on similar topic


#### [CycleMLP: A MLP-like Architecture for Dense Prediction](https://openreview.net/forum?id=NMEceG4v69Y):
What:
- New MLP-based architecture for Images
- Main features:
	- input can be various size
	- linear computational complexity using local windows

Why to read:
- See development of CV and MLP architectures
- Adding small portion of inductive bias helps a lot (Hierarchical Pierceiver)


#### [Language modeling via stochastic processes](https://openreview.net/forum?id=pMQwKL1yctf):
What:
- Use Stochastic process to mitigate problem in "classic" text generation
- Introduced Language model (Time Control) explicitly models latent structure with  
Brownian bridge dynamics learned using a novel contrastive objective 

Why to read:
- better text generation
- Seems fun

#### [Resolving Training Biases via Influence-based Data Relabeling](https://openreview.net/forum?id=EskfH0bwNVn):
What:
- Combine influence function with data relabeling for reduce training bias
- Proposed approach increase model's robustness to label noise
Why to read:
- Numerous aplication in Allegro

#### [Representational Continuity for Unsupervised Continual Learning](https://openreview.net/forum?id=9Hrka5PA7LW):
What:
- Connecting CL and Representation learning
- Propose impovement to UCL to fix catastrophics forgetting and  better qualitative intterpretations.

Why to read:
- Seems to be useful for practitioners (Allegro)



#### [A Fine-Grained Analysis on Distribution Shift](https://openreview.net/forum?id=Dl4LetuLdyK):
What:
- Framework of analysis distribution shift
- Comprehensive analysis of different methods

Why to read:
- See how different approaches can be used to mitigate distribution shift


#### [Weighted Training for Cross-Task Learning](https://openreview.net/forum?id=ltM1RMZntpu):
What:
- New algorithm for cross-tasks learning.
- Representation-based task distance depending on the quality of representations of each tasks.

Why to read:
- Comparison with other modern approaches
- Better domain adaptation pre-training for MailBERT


#### [F8Net: Fixed-Point 8-bit Only Multiplication for Network Quantization](https://openreview.net/forum?id=_CfpJazzXT2):
What:
- 8-bit fixed-point number is able to represent a wide range of values with negligible  
relative error
- New training approach unifying PACT and fixed-point quantization
Why to read:
- References to previous work in field
- Analysis and comparison to previous approaches


#### [Einops: Clear and Reliable Tensor Manipulations with Einstein-like Notation](https://openreview.net/forum?id=oapKSVM2bcj):
What:
- Implemented einops notation
- Comparison on CPU and CUDA
Why:
- einstein notation very convenient operation that simplify writing and reading code.
- PyTorch implementation of einstein operations is rather slow. 


#### [Finetuned Language Models are Zero-Shot Learners](https://openreview.net/forum?id=gEZrGCozdqR):
What:
- Instruction tuning - impove zero-shot learning capabilities via LM FT on various datasets in specific way. 
Why to read:
- Capability of zero-shot 
- See how we can combine SSL and FT with labeled data.



#### [Coordination Among Neural Modules Through a Shared Global Workspace](https://openreview.net/forum?id=XzTtHjgPDsT):
What:
- I don't understand. Some kind of environment for different models communication
Why to read:
- Interesting reference works
- New domain


#### [DISCOVERING AND EXPLAINING THE REPRESENTATION BOTTLENECK OF DNNS](https://openreview.net/forum?id=iRCUlgmdfHJ):
What:
- Discover of *representation bottleneck*
- Design loss functions to mitigate this phenomenon
Why to read:
- Intuition on differences between  DNN and human visual cognition


#### [Compositional Attention: Disentangling Search and Retrieval](https://openreview.net/forum?id=IwJPj2MBcIa):
What:
- Analysis of search/retrieval machanism  in MHA and highlighting problems.
- Solution to the problem: new attention mechanism, that disentangles search and retrieval
Why to read:
- Better understand attention mechanism 


#### [8-bit Optimizers via Block-wise Quantization](https://openreview.net/forum?id=shpkpVXzo3h):
What:
- Using dynamic & block-wise quantization, stable embadding layer new 8-bit optimizer has similar performance to 32-bit Adam by using only fraction of memory.
- Results obtained on multiple tasks 
Why to read:
- Can be directly replacement for 32-bit Adam without drop in metrics


#### [ViTGAN: Training GANs with Vision Transformers](https://openreview.net/forum?id=dwg5rXg1WS_):
What:
- Combining GAN and ViT gives results on par with CNN-based GANs
- Novel techniques regularize ViT.
Why:
- Just for fun


#### [Pixelated Butterfly: Simple and Efficient Sparse training for Neural Network Models](https://openreview.net/forum?id=Nfl-iXa-y7R)
What:
- Using sparse matrix operation to effectively train NN
- Proposed method based on butterfly matrices and simplification useful to train on modern hardware.
Why:
- Learn about sparse model training
- To faster training of GPT-2 and ViT


#### [Linking Emergent and Natural Languages via Corpus Transfer](https://openreview.net/forum?id=49A1Y6tRhaq):
What:
- Analysis of EC and NL. 
Why:
- Learn about emergent communication
- just for fun


#### [Memorizing Transformers](https://openreview.net/forum?id=TrjbxzRcnf-):
What:
- Use non-differentiable memory and approximate kNN to add new information at inference time

Why to read:
- Learn more about memory in LM


#### [EntQA: Entity Linking as Question Answering](https://openreview.net/forum?id=US2rTP5nm_):
What:
- Solve EL as QA
- Invert problem: given document, search "questions" candidate and apply reader to get candidate mentions in document.
Why to read:
- Interesting problem formulation

#### [Strength of Minibatch Noise in SGD](https://openreview.net/forum?id=uorVGbWV5sw):
What:
- Theretical analysis of SGD noise with implication

Why to read:
- New methods: approximation of noise and using LinReg as minimal model for DL. 
- Comprehensive related works section
- Can be useful in practice - sec 6 ( but after review of the section I am not sure :) )


#### [The MultiBERTs: BERT Reproductions for Robustness Analysis](https://openreview.net/forum?id=K0E_F0gFDgA):
What:
- Analysis of BERT models for robustness using novel approach
- Some practical examples of using their method
Why to read:
- Method for quantifying uncertainty of experimental result can be useful


#### [Multitask Prompted Training Enables Zero-Shot Task Generalization](https://openreview.net/forum?id=9Vrb9D0WI4):
What:
- T0
Why to read:
- Analysis of many NLP tasks 



#### [Tuformer: Data-driven Design of Transformers for Improved Generalization or Efficiency](https://openreview.net/forum?id=V0A5g83gdQ_)
What:
- MHSA analysis using tensor diagram
- method for flexible wieght tuning across heads based on data

Why to read:
- Interesting idea (at first glance )



#### [Adversarial Retriever-Ranker for Dense Text Retrieval](https://openreview.net/forum?id=MR7XubKUFB)
What:
- Retriver-Ranker model trained with minimax adversarial objective

Why to read:
- See how problems with negatives sampling and with siamese-style encoding



#### [Normalization of Language Embeddings for Cross-Lingual Alignment](https://openreview.net/forum?id=Nh7CtbyoqV5)
What:
- Word embedding normalization to create better shared vector space for multiple languages

Why to read:
- Important for multilingual NLP tasks and translation



#### [Mapping Language Models to Grounded Conceptual Spaces](https://openreview.net/forum?id=gJcEM8sxHK)
What:
- Experiments with LM to discover whether learned world can be isomorphic to "True" world 

Why to read:
- Better understand how LM learns language
- Learn more about grounding


#### [Leveraging unlabeled data to predict out-of-distribution performance](https://openreview.net/forum?id=o_HsiMPYh_x)
What:
- Predicting target domain accuracy(data on production) with labeled source data(train/val data)
- Experiments performed on images
Why to read:
- Can be useful in practice (model deployment)




#### [Discovering Latent Concepts Learned in BERT](https://openreview.net/forum?id=POTMtpYI1xH):
What:
- Interpretability method based on learned by network "concepts" (linguistic idea)
- New dataset for research on hierarchical concepts 
Why to read:
- One more paper on iterpretability of BERT


#### [Pix2seq: A Language Modeling Framework for Object Detection](https://openreview.net/forum?id=e42KbIw6Wb
What:
- Object detection with model outputing descriptions of bouding boxes and class labels.
- If model can recognise model, we only need to learn how to describe where this object on the picture located.

Why to read:
- Fun
- Compehensive analysis of the model and interesting architecture.



#### [HTLM: Hyper-Text Pre-Training and Prompting of Language Models](https://openreview.net/forum?id=P-pPW1nxf1r)
What:
- LM trained on Hyper-text
- Analysis of prompt efficiency
Why to read:
- See how LM trained on semi-automatically generated text.
- Maybe some hints on noisy text?



#### [ExT5: Towards Extreme Multi-Task Scaling for Transfer Learning](https://openreview.net/forum?id=Vzh1BFUCiIX)
What:
- ExMix collection of 107 supervised NLP tasks for multi-task learning.
- ExT5 model trained with span-denoising C4 obj along with ExMix.t

Why to read:
- Study on tasks transfer.


#### [Should We Be Pre-training? An Argument for End-task Aware Training as an Alternative](https://openreview.net/forum?id=2bO2x8NAIMB):
What:
- studying on online algorithms for pre-training
- better results than in Gururangan

Why to read:
-Inspiration for better domain adaptation


#### [How Low Can We Go: Trading Memory for Error in Low-Precision Training](https://openreview.net/forum?id=YpSxqy_RE84):
What:
- First study on topic

Why to read:
- Looks like good introduction


#### [Knowledge Infused Decoding](https://openreview.net/forum?id=upnDJ7itech):
What:
- Decoding method with the usage of external knowledge
- Method utperform beam search
Why to read:
- Interesting approach to decoding
- useful in many scenarious


#### [Cross-Lingual Transfer with Class-Weighted Language-Invariant Representations](https://openreview.net/forum?id=k7-s5HSSPE5):
What:
- Comprehensive analysis of cross-lingual

Why to read:
- Better understand setup used for training HerBERT

#### [MIDI-DDSP: Detailed Control of Musical Performance via Hierarchical Modeling](https://openreview.net/forum?id=UseMOjWENv)
What:
- Hierachical approach for realistic AND detailed user control.
- Combining Neural and Classical approach.
Why to read:
- Mix of standard and neural approach. Related section can be useful





CHARFORMER: FAST CHARACTER TRANSFORMERS VIA GRADIENT-BASED SUBWORD TOKENIZATION
CONSTRAINING LINEAR-CHAIN CRFS TO REGULAR LANGUAGES
COSFORMER : RETHINKING SOFTMAX IN ATTENTION
PRETRAINED LANGUAGE MODEL IN CONTINUAL LEARNING: A COMPARATIVE STUDY
MOBILEVIT: LIGHT-WEIGHT, GENERAL-PURPOSE, AND MOBILE-FRIENDLY VISION TRANSFORMER
PONET: POOLING NETWORK FOR EFFICIENT TOKEN MIXING IN LONG SEQUENCES
FILIP: FINE-GRAINED INTERACTIVE LANGUAGEIMAGE PRE-TRAINING
LORA: LOW-RANK ADAPTATION OF LARGE LANGUAGE MODELS
STEP-UNROLLED DENOISING AUTOENCODERS FOR TEXT GENERATION
MENTION MEMORY: INCORPORATING TEXTUAL KNOWLEDGE INTO TRANSFORMERS THROUGH ENTITY MENTION ATTENTION
ENHANCING CROSS-LINGUAL TRANSFER BY MANIFOLD MIXUP
TRANS-ENCODER: UNSUPERVISED SENTENCE-PAIR MODELLING THROUGH SELF- AND MUTUAL-DISTILLATIONS
DICTFORMER: TINY TRANSFORMER WITH SHARED DICTIONARY
NO PARAMETERS LEFT BEHIND: SENSITIVITY GUIDED ADAPTIVE LEARNING RATE FOR TRAINING LARGE TRANSFORMER MODELS
EXPLORING EXTREME PARAMETER COMPRESSION FOR PRE-TRAINED LANGUAGE MODELS
