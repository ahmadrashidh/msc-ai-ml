### Spelling Tasks
1. Spelling Error Detection
2. Spelling Error Correction
	- Autocorrect
	- Suggest a correct
	- Suggestion list

### Types of Spelling Errors
1. Non-word Errors i.e. typed any word not in a dictionary
	graffe -> giraffe
2. Real-word Errors i.e. type a word in a dictionary however thats not the word user wanted to type
	- Type Errors - keyboard mistype
	- Cognitive Errors - mistype due to homophone, phonetic spelling, etc

### Correction

#### Non-word Errors:

1. Generate candidates for the misspelled error i.e. real words that are similar to error
2. Choose one which is best using:
	- Shortest Weighted Edit Distance
	- Highest noisy channel probability

#### Real-word Errors
1. For each word w in sentence, generate candidates:
	- candidate word with similar pronunciation
	- candidate word with similar spelling
	- include w in candidate set


### Noisy Channel

- We see an observation $x$ of a misspelled word
- Find the correct word $w$:
	$\hat{w}$ = argmax\[$w\epsilon$V] P($w$|$x$)
	Applying Bayes rule,
	$\hat{w}$ = argmax\[$w\epsilon$V] P($x$|$w$)P($w$)/P($x$)
	$\hat{w}$ = argmax\[$w\epsilon$V] P($x$|$w$)P($w$)
	where equation is called Language Model(which tells how likely the word w is correct word)
	P($w$) -> prior(Unigram Prior Probability)
	P($x$|$w$) -> Likelihood/Channel Model/Error Model probability
	