
Example problems:
Email: Spam/Not Spam?
Online Transactions: Fraudulent (Yes/ No)?
## Why not classification using Linear Regression?

Positive and Negative can be considered as classes

Therefore,
For Univariate Logistic Regression,
$y$ $\epsilon$ {0,1}
where 0 -> Negative Class
1 -> Positive Class

$y$ $\epsilon$ {0,1,2,3} for Multivariate Logistic Regression

Threshold Classifier Output $h(x)$ at 0.5:
if $h(x)$  >= 5, predict y = 1
if $h(x)$  < 0.5, predict y = 0

- While y = 0,1, sometimes, linear regression can provide values greater than 1 / lesser than 0
- A training example which outlay, can cause wrong classification. 

So, linear regression doesn't work for classification.

## Logistic Regression Model

0 <= h(x) <= 1

h(x) = g($\theta$<sup>T</sup>x)

=> g(z) = 1 / (1 + e<sup>-z</sup>)

where g(z) -> sigmoid function/ logistic function

### Interpretation of output

h$\theta$(x) => estimated probability that y = 1 for input x
=> P(y=1|x;$\theta$) -> probability that y = 1, given x, parameterised by $\theta$

### Decision Boundary

h(x) = g($\theta$<sup>T</sup>x)

y = 1 if h(x) >= 0.5
otherwise h(x) < 0.5

g(z) = 1 / (1 + e<sup>-z</sup>)

g(z) >= 0.5
when z >= 0
that is, when $\theta$<sup>T</sup>x >= 0

h(x) = g($\theta$<sub>0</sub> + $\theta$<sub>1</sub>x<sub>1</sub> + $\theta$<sub>2</sub>x<sub>2</sub> ) for $\theta$ = \[-3,1,1,]
=> $\theta$<sup>T</sup>x = $\theta$<sub>0</sub> + $\theta$<sub>1</sub>x<sub>1</sub> + $\theta$<sub>2</sub>x<sub>2</sub>
y = 1 if $\theta$<sup>T</sup>x >= 0
=> $\theta$<sub>0</sub> + $\theta$<sub>1</sub>x<sub>1</sub> + $\theta$<sub>2</sub>x<sub>2</sub> >= 0
-3 + x<sub>1</sub> + x<sub>2</sub> >= 0

x<sub>1</sub> + x<sub>2</sub> >= 3, which is a straight line called decision boundary

But decision boundary is defined by parameter $\theta$, not dataset x. Training dataset is used to fix the parameter.

### Cost function

J($\theta$) = (1/m). $\Sigma$ i -> m (1/2) (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup>

where (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup> => Cost(h(x<sup>i</sup>),y<sup>i</sup>)

Cost(h(x<sup></sup>),y) = (h(x) - y)<sup>2</sup>
For Sigmoid Function, Cost(h(x<sup></sup>),y) will not be convex function, only where gradient descent converge into optimum value

So, the cost equation for Logistic Regression:
Cost(h(x<sup></sup>),y) = -log(h(x)) if y = 1
					-log(1 - h(x)) if y = 0

if y = 1 and h(x) = 0, cost function tends to infinity
if y = 0 and h(x) = 1, cost function tends infinity.

### Simplified Cost function


J($\theta$) = -1/m \[ $\Sigma$ i -> m (y<sup>i</sup>.log(h(x<sup>i</sup>)) - (1-y<sup>i</sup>).log(1 - h(x<sup>i</sup>))]

Fit parameters $\theta$:

$\theta$<sub>j</sub> := $\theta$<sub>j</sub> - $\alpha$. (1/m). $\Sigma$ i -> m (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup>.x<sup>i</sup><sub>j</sub>









