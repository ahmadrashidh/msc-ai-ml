
The perceptron belongs to the category of supervised learning algorithms, single-layer binary linear classifiers to be more specific.

Activation Function - g(z)

z = $\sum$ (1 to m) x<sub>j</sub>w<sub>j</sub> =  w<sub>1</sub>x<sub>1</sub> + ... + w<sub>m</sub>x<sub>m</sub> = w<sup>T</sup>x
where w -> feature/weight vector
x -> m samples

if g(z) > $\theta$ (threshold), predict 1 or -1

g(z) is called Unit Step Function/ Heaviside Step Function

Unit Step Function means:

0 if z < 0 otherwise 1
in our case,
-1 if g(z) < $\theta$, otherwise 1

### Initial Perceptron Rule

Rosenblatt’s initial perceptron rule is fairly simple and can be summarized by the following steps:

1. Initialize the weights to 0 or small random numbers.
2. For each training sample x(i)�(�):
    1. Calculate the _output_ value.
    2. Update the weights.

wj:=wj+Δwj
Δwj=η(target<sup>(i)</sup>−output<sup>(i)</sup>)x<sup>(i)</sup><sub>j</sub>
where
η -> learning rate
target -> true class label
output -> predicted class label

### Problems with Perceptron

-  it cannot draw decision boundary for data that is not linearly separable
- stops updating weights as soon as all samples are classified correctly -------------------------------------Why?

## Adaline - ADAptive LInear NEuron 

In Adaline, g(z) is linear activation function instead of unit step function.

Δw =−η.∇J(w)

Δwj =−η.∂J/∂w<sub>j</sub>

∂J/∂w<sub>j</sub> = ∑(t<sup>(i)</sup>−o<sup>(i)</sup>)(−x<sup>(i)</sup><sub>j</sub>)

Δwj = η.∑(t<sup>(i)</sup>−o<sup>(i)</sup>).x<sup>(i)</sup><sub>j</sub>


This is also called batch gradient descent



