w


## Research report 0


Aim: 
	Train model with relatively small number of parameters, but with few-shot capabilities. We assume, that will be general model for polish language

Initial setup:
	- Data for training: the same as for HerBERT 
	- Data for evaluation: subset of KLEJ or/and LEPISZCZE
	- num of effective parameters: 1 billion
	- final  ability: in-context learning or prompt 
	- baseline to compare: HerBERT FT on small number of parameters + parameter-efficient FT (e.g.  adapters)
	- Training procedure: ?
	- hardware: ?

Research questions:
	- How can we train model to have **strong**  few-shot ability on 1b parameter model?

- Allegro use
	- Is it possible to make domain adaptation on allegro data for such model?
	- Can we make effective usage of 1b model in Allegro production setup?
	- Do we actually need few-shot scenario? Maybe, parameter-effective methods are enough
	
Practical research questions
	- If we wan't few-shot model for Polish and show how to get emergent abilitis from big models on small one, 
	we should have or at least prognose large model performance 



# Research report 1

- Clarify definitions and methodology around few-shot learning +
- Focus on papers that show whether it is possible to get few-shot performance on ~1b models?
- Can we tune HerBERT or plT5 to get few-shot performance?


### Definition of few-shot

few-shot - we don't train model and use prompt to show X examples for model, to "learn on fly" . Based on X, we say X-shot learning



### [Mosaic ML blogpost on cheap training of LLM ](https://www.mosaicml.com/blog/gpt-3-quality-for-500k)

- They use Chinchilla paper to train compute-optimal model with 1.3b of parameters for only 2000$ 
- _All training runs were profiled with Composer on a 256xA100-40GB cluster with 1600Gbps RoCE interconnect, using a global batch size of 2048 sequences ~= 4M tokens._
![[Pasted image 20221221014101.png|900x150]]

Recipe for such effective training:
- https://docs.mosaicml.com/en/v0.10.0/ - Library for training
- Handling of spikes and crashing - it is important, because this type of errors are very common in multi-node training
	- effective dataloading process for continuation should be used
- Use  [**PyTorch FSDP**](https://pytorch.org/docs/stable/fsdp.html) (FullyShardedDataParallel) as desing choice for handling multiple machines and GPUs
	- model only has to fit within _the total cluster memory_, not within each GPU.
		- NOTE: We can calculate ~ how much cards we need for training 1b model using sum of memories
		- TODO: Learn how to calculate size for such parameters
- Based on Chinchilla research, we can have performance gain with increasing size of dataset, not number of parameters





### [GPT-NeoX-20B: An Open-Source Autoregressive Language Model](https://arxiv.org/abs/2204.06745)
- open source GPT-like models with different size. Should help to see few-,zero-shot capabilities  of 1b model 
- considers only AUTOREGRESSIVE models
- Evaluation of Eleuther.ai models with Open AI API. 
	- As GPT-3 they use OpenAI API, and sizes are estimated by framework  - 350M (Ada), 1.3B (Babbage), 6.7B (Curie), and 175B (Da Vinci).
	- ![[Pasted image 20221227141156.png|600x300]]

- Evaluation of fairseq (Artetxe paper) model on the same data. yellow - more params, better perf.; red - differnt behaviour; green - inverse scaling 
	- ![[Pasted image 20221227150944.png|600x300]]

Paper results:
-  GPT-J-6B and GPTNeoX-20B benefit substantially more from fewshot evaluations than the FairSeq models do.
	- не совсем ясно с чем это связано 
- 1b models have some few-shot capabilities, but without additional techniques scaling is the most effeective way to increase metrics


## Outcomes:
- It is possible for us to train 1b model on compute-optimal number of tokens (Mosaic)
- basic training of 1b model wouldn't be effective for few-shot performance. Nevertheless, such model show some few-shot capabilities comparable to LLM