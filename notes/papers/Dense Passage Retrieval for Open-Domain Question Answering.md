
#### Introduction

This paper focuses on improving Retriever part of QA systems, switching to dense representations obtained from BERT. Another important novelty, they show how to train such retrievers using metric learning approach, which can be used to train in multi-task regime.

And, what authors emphasized, that they introduce training procedure without pretraining encoder (as in ORQA and REALM)

- Using BM25 and dense encoding is complementary by design. because former based on syntactic features and later focus on semantic similarity.
- Dense encoding is learnable, so convinient for task-specific tuning 
- "we focus on developing the right training scheme using a relatively small number of question and passage pairs."



#### Methods

We focus on Retriever component, because there is only novelty. Reader is the standard span-based model.

##### Retriever
Two encoders, $E_Q$  and $E_P$ encoding question and passages correspondingly.
During training we use $E_P$ to encode answers, but in the run-time we using only $E_Q$ to encode question and perform MIPS on encoded passages set (encoded with trained $E_P$) .
During inference, using similarity function to get top-k passages
$$

sim(q,p) = E_Q(q)\top E_P(P)

$$

##### Training
We train on question-answer pairs. Having batch with m instances, we want dot-product similarity to become good ranking function for retrieval. Authors used metric learning approach to train such encoders. During tre training they want to have spae where question and answer (possitive passage) are closer, thatn same question and other answers in batch. In terms of metric learning, for  $question_i$ , $answer_i$ is possitive, while $answer_{1...m\i}$ is negative, so they should be ranked lower comparing to positive. Loss function is negative log likelihood of the positive passage:

$$
L\left(q_{i}, p_{i}^{+}, p_{i, 1}^{-}, \cdots, p_{i, n}^{-}\right)=-\log \frac{e^{\operatorname{sim}\left(q_{i}, p_{i}^{+}\right)}}{e^{\operatorname{sim}\left(q_{i}, p_{i}^{+}\right)}+\sum_{j=1}^{n} e^{\operatorname{sim}\left(q_{i}, p_{i, j}^{-}\right)}}$$
Additional to gold batch negatives,  one BM25 negative passage per question is used

Experiemental setup
- Because only pairs of questions and answers are provided in TREC, WebQuestions and TriviaQA6, we use the highest-ranked passage from BM25 that contains the answer as the positive passage. If none of the top 100 retrieved passages has the answer, the question will be discarded.
- we train a multidataset encoder by combining training data from all datasets excluding SQuAD (biased on small set of Wikipedia articles



#### Ablation Study on Model Training
- **Sample efficiency** - using pretrained LM overperform BM25 using small number of examples (~1000). Using more examples futher impoves retrieval accuracy
- **In-batch negative training** - 1 BM25 example (high bm25 score + no answer string in passages) substantially improves scores + in-batch negatives help a lot and outperform random negatives and more bm25 examples.
- **Cross-dataset generalization** -  scores below directly FT models, but only a few 3-5 PP