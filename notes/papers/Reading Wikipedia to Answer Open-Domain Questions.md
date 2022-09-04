This paper can be considered as starting point in two-stage NN QA models - paradigm that will be highly popular in the next years. For this systems we should have data in form of text (not structured, internal data source) that we anticipate to find the answer to the question and approach that handles every of the stages - not important whether it is one model or not NN model.

1. Document Retriever
Given question we perform search over internal data source (for open form QA this source is Wikipedia almost all time) to retrieve similar to question document. 
DRQA uses efficient (non-machine learning) document retrieval system to choose document that will be read more carefully on second stage

description from paper on this retrievers:
"""
A simple inverted index lookup followed by term vector model scoring performs quite well on this task for many question types, compared to the built-in ElasticSearch based Wikipedia Search API (Gormley and Tong, 2015). Articles and questions are compared as TF-IDF weighted bag-ofword vectors. We further improve our system by taking local word order into account with n-gram features. Our best performing system uses bigram counts while preserving speed and memory efficiency by using the hashing of (Weinberger et al., 2009) to map the bigrams to 2^24 bins with an unsigned murmur3 hash.
"""

Output of this model  is N the most similar to question documents that will be processed on stage 2 with Document Reader 

2. Document Reader

On high level idea is pretty simple: use Glove to embed paragraphs tokens and questions. Using paragraphs vectors and question vector train two independent classifiers that output probability for every paragraphs's token to be START or END of answer span. Choose span where START_idx <= END_idx and P_start(i) * P_end(i') is maximized.


More detailed description

**Paragraphs encoding**
Two stage procedure:
1. Prepare feature vectors

Every word vector consist of:
- GloVe embedding (+fine-tune 1000 most frequenst question words)
- Matching with question words
- POS feature
- NER feature
- Term frequency
- Aligned question embedding - sum of question words weighted by similarity with passage word (attention).
  This feature add soft alignment between similar non-identical words

2. Encode feture vectors using RNN



**Question encoding**
another RNN encodes embedded question into single $q$ vector 
$$
q=\sum_j b_jq_j, \space where \space b_j - \text{encodes importance of each question word}\newline
$$

$$
b_j = \frac{exp(w * q_j)}{\sum_{j'}{exp(w * q_{j'})}}\text{, where w is a weight vector to learn.}
$$


**Prediction**
Having question vector  vector $\textbf{q}$  and paragraph vectors $\{p_1,...,p_m\}$  we train two independent classifiers to predict [[answer span]] start and end token. 
$$
\begin{align}
P_{start}(i) \propto exp(\textbf{p}_i \textbf{W}_s \textbf{q}) \\
P_{end}(i) \propto exp(\textbf{p}_i \textbf{W}_e \textbf{q})
\end{align}
$$
Having probabilities of start and end token for every $p_i$   final [[answer span]] will be start from token $i$ to token $i'$ , where $i \leq i' \leq i+15$  and $P_{start}(i) * P_{end}(i')$  is maximized.  To have comparible scores across documents, authors uses unnormalized exponential and take argmax over all possible spans in documents retrived from the first stage.


**Data**
SQuAD, CuratedTREC, WebQuestions, WikiMovies

