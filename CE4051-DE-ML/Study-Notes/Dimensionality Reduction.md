
Reasons why Dimensionality Reduction:
1. compress the data
2. speed up learning algorithm

## Data Compression
> Reduce data from higher dimension to lower dimension

Creating a new, lower dimensional feature space, and then creating a new set of samples in that space by projecting the original samples on to the lower-dimensional space. This speeds up learning algorithms.

__Preprocessing__(feature scaling/ mean normalisation):

$\mu$<sub>j</sub> = 1/m $\sum$ 1 -> m \[x<sup>(i)</sup><sub>j</sub>]
Replace x<sup>(i)</sup><sub>j</sub> with x<sub>j</sub> - $\mu$<sub>j</sub>

## Principal Component Analysis (PCA)


To reduce n dimensions to k dimensions: 
Find k vectors u<sup>1</sup>,u<sup>2</sup>,...,u<sup>k</sup> $\epsilon$ R<sup>n</sup>) onto which to project the data so as to minimise the projection error.

1. Compute covariance matrix
	=> 1/m $\sum$ 1 -> n \[x<sup>i</sup> .(x<sup>i</sup>)<sup>T</sup>]
	



