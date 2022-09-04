Introduction



Model
Both pre-training and fine-tuning uses similar paradigm: retrieve-then-predict, so this can be seen as standard two-stage QA pipeline with modification in second depending on tasks: during pre-training we use retrieved data to perform MLM, during fine-tuning it is Open-QA task: given question predict answer
$$
\begin{align*}
x - input \newline
y - output \newline
Task: p(y|x)
\end{align*}
$$

REALM decompose $p(y|x)$ into two steps: 
retrieve - given $x$ we retrieve helpful documents $z$ from a knowledge corpus $Z$. 
Predict - having $x$ and $z$ perform prediction of y

To obtain $p(y|x)$ we treat z as latent variable and marginalize over all possible retrieved documents:
$$
p(y|x) = \sum_{z \in Z} p(y| z,x)p(z|x)
$$
Coming to architecture, lets $p(z|x)$ denotes neurall knowledge retriever, and $p(y|z, x)$ knowledge-augmented encoder.



**Knowledge Retriever**
$$
\begin{align}
p(z|x) = \frac{exp\space f(x,z)}{\sum_{z'}exp\space f(x, z')}\newline
f(x,z) = Embed_{input}(x)^{\top}Embed_{doc}(z)
\end{align}
$$
To obtain embedding we use BERT model

**Knowledge-Augmented Encoder**
After that, we concatenate question and retrieved documents into one string split by "SEP" token and feed into another Transformer-based model.
Depend on task procedure slightly differs
pre-training - predict masked tokens in $x$ 
fine-tuning - predict answer string, which we assume can be found in retrieved document z
$$
\begin{aligned}
p(y \mid z, x) & \propto \sum_{s \in S(z, y)} \exp \left(\operatorname{MLP}\left(\left[h_{\mathrm{START}(\mathrm{s})} ; h_{\mathrm{END}(\mathrm{s})}\right]\right)\right) \\
h_{\mathrm{START}(\mathrm{s})} &=\operatorname{BERT}_{\mathrm{START}(\mathrm{s})}\left(\text { join }_{\mathrm{BERT}}\left(x, z_{\mathrm{body}}\right)\right) \\
h_{\mathrm{END}(\mathrm{s})} &=\operatorname{BERT}_{\mathrm{END}(\mathrm{s})}\left(\mathrm{join}_{\mathrm{BERT}}\left(x, z_{\text {body }}\right)\right)
\end{aligned}
$$




**Training**

![[Pasted image 20220610063141.png]]
**MIPS**
The most important difference with other models, authors tries to refresh index by asynchronously re-embedding and refresh MIPS index. For that they use 2 jobs :
"a primary trainer job, which performs gradient updates on the parameters, and a secondary index builder job, which embeds and indexes the documents"



Additional strategies:
- If pre-training corpus and document corpus are the same, some retrieval can be a form of leak and training degrades and model starts to look for exact string match.
- Using salient span masking really helps to make MLM masking more difficult. Authors used NER BERT-based model to identify and mask entities and re to mask dates. This significantly improve performance
-  Null document to model situation when additional knowledge is not neccessary
- Warm-up BERT encoders for question and document with ICT 


Analysis
Small section in paper