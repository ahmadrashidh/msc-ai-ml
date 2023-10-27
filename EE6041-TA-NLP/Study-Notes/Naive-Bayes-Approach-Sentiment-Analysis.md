Occurrence of the word more significant than frequency
So, we bring Binary Multi-nominal Naive Bayes

## Binary Multi-nominal Naive Bayes (Binary NB)
> Clip word count to 1 for every document before calculating likelyhood


## Dealing with Negation

For example, I don't like the movie or don't dismiss him

Add NOT_ to every word between negation and next punctuation


## Lexicons
- Pre-built word lists when don't have enough labelled training data

## Evaluation of Text Classification

- Truth Table
Precision -> % of selected items that are correct
Recall -> % of correct items that are selected

Accuracy = TP + TN / TP + FP + FN + TN
Precision = TP / TP + FP
Recall = TP / TP + FN

### A combined measure
> or F-measure assess P/R tradeoff known as weighted harmonic mean

F = 2PR/P+R