
### Datasets
[Multi2WOZ: A Robust Multilingual Dataset and Conversational Pretraining for Task-Oriented Dialog](https://aclanthology.org/2022.naacl-main.270/)
- use multilingual model as pre-trained starting point; use other languages as augmentation
 [EVI: Multilingual Spoken Dialogue Tasks and Dataset for Knowledge-Based Enrolment, Verification, and Identification](https://aclanthology.org/2022.findings-naacl.124.pdf)
- Not relevant spoken dialogues, but they have Polish language


### Various
 https://www.amazon.science/alexa-prize - review of the solutions from challenges, especially TaskBot Challenge
[Learning Dialogue Representations from Consecutive Utterances](https://aclanthology.org/2022.naacl-main.55/)
- Use consecutive utterances pair (i, i+1) as positives in contrastive learning, because it has natural semantic relation. Shows that method helps learn better dialog representations (but they use simple baselines)
 [Fast and Light-Weight Answer Text Retrieval in Dialogue Systems](https://aclanthology.org/2022.naacl-industry.37/)
- Comparison of the small retrieval models that can be used in production
 [Lightweight Transformers for Conversational AI](https://aclanthology.org/2022.naacl-industry.25/)
 - Description of pre-training procedure to get better dialogue representation using NLU models.
[Long-term Control for Dialogue Generation: Methods and Evaluation](https://aclanthology.org/2022.naacl-main.54/)
- Generate response with consideration of the future turns. E.g. If we need to ask about order date, delivery method we teach model to make this "step-by-step" (multiple turns), not all in one responce
[Building a Role Specified Open-Domain Dialogue System Leveraging Large-Scale Language Models](https://aclanthology.org/2022.naacl-main.155/)
- Different queues can be treated as different roles of one model
[BORT: Back and Denoising Reconstruction for End-to-End Task-Oriented Dialog](https://aclanthology.org/2022.findings-naacl.166/)
- Example how we can fix erroneous prediction made during previous turn.



### Knowledge-augmentation in dialogue	
[Database Search Results Disambiguation for Task-Oriented Dialog Systems](https://aclanthology.org/2022.naacl-main.85/)
- How process multiple returned results from Database
[Knowledge-Grounded Dialogue Generation with a Unified Knowledge Representation](https://aclanthology.org/2022.naacl-main.15/)
- Experiments on puting different sources of knowledge into one format
[Learning to Express in Knowledge-Grounded Conversation](https://aclanthology.org/2022.naacl-main.164/)
-Split user response on structure and style. Helps discover underlying pattern of knowledge expession  
[KETOD: Knowledge-Enriched Task-Oriented Dialogue](https://aclanthology.org/2022.findings-naacl.197/)
- Based on knowledge generate additional(chit-chat) text in TOD


### Evaluation
[Explaining Dialogue Evaluation Metrics using Adversarial Behavioral Analysis](https://aclanthology.org/2022.naacl-main.430)
- Test robustness of metrics that we use (I only remember, that I liked this paper during oral presentation)
[Let’s Chat: Understanding User Expectations in Socialbot Interactions](https://aclanthology.org/2022.hcinlp-1.5.)
- Slight inspiration to analyse user's expectations from chatbot 
[Automating Human Evaluation of Dialogue Systems](https://aclanthology.org/2022.naacl-srw.29/)
- BERT classifier based on human assesment (from student research workshop:) )
 [Diversifying Neural Dialogue Generation via Negative Distillation](https://aclanthology.org/2022.naacl-main.31)
- use this method to teach model what shouldn't be generated