	## Elitism
> Always copy the n best individuals

- Slightly convoluted with DEAP
- but problem is Good individuals/schemata being destroyed

## Tournament Selection

1. Choose k individuals at random
2. Select the best or two

- Pros:
	- No need to sort whole population
- k -> selection pressure - it means how likely are we to choose the best individuals
- k need to be chosen - on Convergence vs Diversity tradeoff

## Generalisation

Parent -> $\lambda$
Offspring -> $\mu$
($\lambda$, $\mu$) - Comma Strategy
- Form a population of  $\lambda$ parents, create $\mu$ offspring
- Form a new population from offspring
+ No generation gap
- More exploratory
- Best fitness can decrease
($\lambda$ + $\mu$) - Plus Strategy
- Form a population of  $\lambda$ parents, create $\mu$ offspring
- Form a new population from entire set of individuals - so best in parents remain
- Harder to break out of local maxima
