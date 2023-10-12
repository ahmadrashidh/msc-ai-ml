
# Text Classification

- Assigning subject categories, topics, or genres
- Span Detection
- Authorship identification
- Age/gender identification
- Language Identification
- Sentiment Analysis and etc

## Task of Text Classification

Input:
- Document d
- A Fixed Set of classes C = {c1,c2,c2}
Output: a predict class of the document

### Hand-coded rules

Input:
- Rules i.e. combinations of words or other features like from address

- High accuracy
- Expensive maintenance

### Supervised Machine Learning

Input:
- Document d
- A Fixed Set of classes C = {c1,c2,c2}
- Training examples of m hand-labelled documents (d<sub>1</sub>,c<sub>1</sub>),...,(d<sub>m</sub>,c<sub>m</sub>)
Output:
- A learned classifier that d->c

#### Naive Bayes Classifier
> Classifier based on Baye's Rule


- Bag of words that keeps count of how many times a word occurs
- Map every words to class

For a document d and a class c

$P(c|d)$ = ${P(d|c).P(c)}/{P(d)}$

Best class C = argmax $P(c|d)$
=> argmax ${P(d|c).P(c)}/{P(d)}$
Eliminating constant
=> argmax ${P(d|c).P(c)}$

__Assuming__
- Position of word doesn't matter
- Feature probability (P(x<sub>i</sub>|c<sub>j</sub>) are independent given the class c.


C = argmax P(x<sub>1</sub>, x<sub>2</sub>,...,x<sub>n</sub>).P(c)
C = argmax P(c<sub>j</sub>) P(x | c) for every feature in set of features

Using log-space to avoid underflow


C = argmax\[ log P(c<sub>j</sub>) + $\sum$ log P(x<sub>j</sub> | c<sub>j</sub>)

### Multinomial Naive Bayes Model

First Attempt: Maximum Likelihood Estimates

P(c<sub>j</sub>) = doccount(C = c<sub>j</sub>) / N<sub>doc</sub>
P(w<sub>i</sub>|c<sub>j</sub>) = count(w<sub>i</sub>|c<sub>j</sub>) / $\sum$ count(x | c<sub>j</sub>)

where N -> number of documents
doccount(C = c<sub>j</sub>) -> how many of them are in class j
P(w<sub>i</sub>|c<sub>j</sub>) -> fraction of times word w<sub>i</sub> appears among all words in documents of topic c<sub>j</sub>


Add-one smoothing
P(w<sub>i</sub>|c<sub>j</sub>) = count(w<sub>i</sub>|c<sub>j</sub>) + 1 / $\sum$ (count(x | c<sub>j</sub>) + 1)

Steps:
1. From training corpus, extract Vocabulary V
2. Calculate P(c<sub>j</sub>) terms
	For each c<sub>j</sub> in C do
	docs<sub>j</sub> <- all docs with class = c<sub>j</sub>
3. calculate P(c<sub>j</sub>) <- docs<sub>j</sub> / total number of docs
4. Calculate P(w<sub>k</sub>|c<sub>j</sub>) terms
	- Text<sub>j</sub> <- single doc containing all docs<sub>j</sub>
	- For each word w<sub>k</sub> in V
			n<sub>k</sub> <- no. of occurrences of w<sub>k</sub> in Text<sub>j</sub>

		P(w<sub>k</sub>|c<sub>j</sub>) = (count(w<sub>i</sub>|c<sub>j</sub>) + 1) / n<sub>k</sub> + 1 |V|)

__Stop words__

- Remove stop words - very frequent words - from both training and test sets


## Generative Model for Multinomial Naive Bayes



