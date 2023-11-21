
Logistic Regression Cost Function for NN:

$J(\theta) = \frac{-1}{m} \sum_{j=1}^m \sum_{k=1}^K y^i_k.log(h(x^i))_k - (1-y_k^i).log(1 - h(x^i))_k] + \frac{\lambda}{2m}\sum_{l=1}^L$$\sum_{i=1}^{s_l}$$\sum_{j=1}^{s_{l+1}} (\theta_{ji}^l)^2$

where K => number of output units
L -> number of hidden layer
s<sub>l</sub> -> number of units in l<sup>th</sup> layer

## Back-propagation

min $J(\theta)$
=> $\frac{\partial J(\theta)}{\partial \theta_{ji}^l}$

Intuition: $\delta_j^{(l)}$ = "error" of node j in layer l

For each output unit layer, for eg L = 4
$\delta_j^{(4)}$ = $a_j^{(4)} - y_j$
where $a_j^{(4)}$ -> $h_{\theta}(x)_j$
$\delta^{(3)}$ = ${\theta^{(3)}}^T\delta^{(4)}.*g'(z^{(3)})$ 
where * is element-wise multiplication between matrices

Back-propagating to do the error calculation

$\frac{\partial J(\theta)}{\partial \theta_{ji}^l}$ = $a_j^{(l)}\delta_i^{(l+1)}$ if $\lambda$ = 0

