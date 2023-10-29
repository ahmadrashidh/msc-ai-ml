Goal: Compute the probability of a sentence or sequence of words
$P(w) = P(w_1,w_2,w_3,...w_n)$

A task, Probability of an upcoming word given previous word:

$P(w_5 | w_1,w_2,w_3,w_4)$

$P(w)$ or $P(w_5 | w_1,w_2,w_3,w_4)$ is called language model (LM)

### Joint Probability of words in sentence

__Chain Rule of Probability__:
P(A,B,C,D) = P(A).P(B|A).P(C|A,B).P(D|A,B,C)

P(its water is so transparent) = P(its) x P(water | its) x P(is | its water) x P(so | its water is) x P(transparent | its water is so)


## Markov Assumption

P(the | its water is so transparent that) == P(the | that)

or 

P(the | its water is so transparent that) == P(the |  transparent that)

## Unigram Model

$P(w_1,w_2,w_3,...w_n) = \prod P(w_i)$


## Bigram Model

$P(w_1,w_2,w_3,...w_n) = \prod P(w_i | w_{i-1})$

N-gram Model is insufficient model of language due to its long-distance dependencies


### Estimating Bigram probabilities

__Maximum Likelihood Estimate__:

$P(w_i | w_{i-1}) =\frac{count(w_{i-1},w_i)}{count(w_{i-1})}$

Of all the times word $w_{i-1}$ occurred, how many times it occurred followed by word $w_i$

