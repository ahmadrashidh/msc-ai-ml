
## Linear Regression with one variable
> Also called as Univariate Linear [[Regression]] for it has only one independent/feature variable

**Terminology**
Training Set = dataset used to train the model


**Notations:**
m = number of training examples
X - inputs/features
Y - outputs/targets
x = input/feature variable
y = output/target variable
(x,y) = a single training example
(x<sup>(i)</sup>, y<sup>(i)</sup>) = i<sup>th</sup> training example where i = 1...m is a specific row in the datatable
Hypothesis (h) = X -> Y

### Linear Regression Model

**Process**: Training Set -> Learning Algorithm => h (hypothesis or model)

**Algorithm**: feature(X) -> f(x) => prediction($\hat{y}$) where f(x) => hypothesis

**Mode**: $\hat{y}$ = f(x) = $f_{w,b}(X) = wx + b$
where w,b are parameters
$\hat{y}$ is predicted output
OR
Parameterised: $h(x) =\theta_0 + \theta_1x$
h(x) -> hypothesis
$\theta$<sub>0</sub> , $\theta$<sub>1</sub> -> population parameters

Parameters are also called coefficients or weights

### Explanation of Linear Regression Model

The line fitted for the dataset is different for different values of parameters. Goal of the problem is to find w,b that defines $\hat{y}$ which is close to all $y^{(i)}$ for all ($x^{(i)},y^{(i)}$).
### Cost Function

Cost function is used to define values for w, b so that $\hat{y}$ is so close to $y$ for our training examples (x,y) i.e. low residual/error

That is,
($\hat{y} - y$) should be small

mathematically,
compute for every datapoint, $\sum_{i=1} ^m (\hat{y}^i - y^i)^2$

Averaging
=>  $\frac{1}{2}m\sum_{i=1} ^m m(\hat{y}^i - y^i)^2$

therefore, 
J(w,b) = $\frac{1}{2}m\sum_{i=1} ^m m(\hat{y}^i - y^i)^2$

J(w,b) -> Cost function or Squared Error Function 

### Intuition of cost function in regression

Model: $f_{w,b}(x) = wx + b$
Parameters: w, b
Cost Function: $\frac{1}{2}m\sum_{i=1} ^m m(\hat{y}^i - y^i)^2$
Goal: minimize J(w, b)

> W.r.t Linear Regression Cost function is convex function as it doesn't have local optimum but only global optimum

When w = 0, and for various values of  b for same x, it will from parabola, therefore, need to find optimum cost function where it is closest to x-axis

When w != 0, b != 0 for same x, it will from dough-shaped place.

Note: In 3D, this is visualised in contour plots
### Gradient Descent
> Minimises a function

in our case, minimise over w,b of function J(w, b)

$\theta$<sub>j</sub> := $\theta$<sub>j</sub> - $\alpha$ d/d$\theta$<sub>j</sub>(J($\theta$<sub>0</sub> ,$\theta$<sub>1</sub>))
$\alpha$ - learning rate
if $\alpha$ is too small, gradient descent can be slow. Otherwise, descent can overshoot the minimum point, may fail to converge or even diverge.

However, with fixed learning rate, as we approach local minimum, gradient descent will take smaller steps automatically as derivative will be smaller at every step

## Gradient Descent For Linear Regression

Each gradient descent uses all training examples, therefore called Batch Gradient Descent

$\theta$<sub>0</sub> := $\theta$<sub>0</sub> - $\alpha$. (1/m). $\Sigma$ i -> m (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup>

$\theta$<sub>1</sub> := $\theta$<sub>1</sub> - $\alpha$. (1/m). $\Sigma$ i -> m (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup>.x<sup>i</sup>


## Multivariate Linear Regression

Adds more notations:
n = number of features
x<sup>i</sup> = i<sup>th</sup> training example ( list of features can be represented as vector)
x<sup>i</sup><sub>j</sub> = value of feature j in i<sup>th</sup> training example


h(x) = $\theta$<sub>0</sub> + $\theta$<sub>1</sub>x<sub>1</sub> + $\theta$<sub>2</sub>x<sub>2</sub>  + $\theta$<sub>3</sub>x<sub>3</sub>  ... + $\theta$<sub>n</sub>x<sub>n</sub> 
    =>  $\theta$<sub>0</sub>x<sub>0</sub> + $\theta$<sub>1</sub>x<sub>1</sub> + $\theta$<sub>2</sub>x<sub>2</sub>  + $\theta$<sub>3</sub>x<sub>3</sub>  ... + $\theta$<sub>n</sub>x<sub>n</sub> 
    => $\theta$<sup>T</sup>x where x<sub>0</sub> -> 1 ( just for computation efficiency)

### Cost Function 
The parameter of function J becomes $\theta$ vector

### Gradient Descent

for n features: 
$\theta$<sub>j</sub> := $\theta$<sub>j</sub> - $\alpha$. (1/m). $\Sigma$ i -> m (h(x<sup>i</sup>) - y<sup>i</sup>)<sup>2</sup>.x<sup>i</sup><sub>j</sub>

#### Feature Scaling

Make sure values of different feature are on a similar scale - to converge quickly or have better gradient descent

So, scaling. Nothing average with highest value of feature.

Get every feature into approx -1 <= x<sub>j</sub> <= 1

**Mean Normalisation**

x<sub>i</sub> = x<sub>i</sub> - $\mu$<sub>i</sub> / max(x<sub>i</sub>)

#### Choosing learning rate

One thought: Declare convergence is cost decreases by less than 10<sup>-3</sup>

Can be thought by observing cost vs no. of iterations/epochs

If the cost increases and decreases - decrease learning rate

Try - range of values




