## Background

__Bias__
- phenomenon that skews the result of an algorithm in favour or against an idea.
-  considered a systematic error that occurs in the machine learning model itself due to incorrect assumptions in the ML process.

__Variance__
- variance is the variability in the model prediction—how much the ML function can adjust depending on the given data set. Variance comes from highly complex models with a large number of features.

High Bias -> Low Variance and vice versa
High Bias -> Under-fitting
High Variance -> Over-fitting

__Overfitting__
> If we have too many features, hypothesis may fit but fail to predict/generalise on new samples, it is called overfitting

Addressing overfitting:
1. Reduce number of features
	- Manually select features to keep
	- Model Selection Algorithm
	It is like throwing details which might be important
2. Regularisation
	- Keep all the features but reduce magnitude/values of $\theta$
	- Each feature contribute a bit to predicting y

## Intuition

Small values for parameters
- Simpler Hypothesis
- Less Prone to overfitting

## Cost Function

Regularisation parameter
=> $\lambda$ $\sum_{j=1}^n$ $\theta$<sub>j</sub><sup>2</sup>   
where $\lambda$ -> Tuning Parameter

Cost Function becomes:
minimize (1/2m) $\sum_{i=1}^m$ (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup> + $\lambda$ $\sum_{j=1}^n$ $\theta$<sub>j</sub><sup>2</sup>   
