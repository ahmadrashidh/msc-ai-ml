
> Dimensionality Reduction Method that utilises information about the class of each data point to produce transformation that preserves information in the dataset

## Why LDA?

- PCA doesn't consider labels for classes
- Not optimal for classification as lose discrimination

## Whats LDA?
> Transform data to line that preserves direction useful for data classification

## Transformed Data Means

- Uses statistical properties of the data to find line that is optimum for classification
- Project x<sub>i</sub> into unit vector v, which is equal to v.xi = v<sup>T</sup>x<sub>i</sub> 
- Mean of transformed data $\hat{u}$<sub>1</sub>, $\hat{u}$<sub>2</sub>
	$\hat{u}_1 = \frac{1}{n_1} \sum_{x_i=c_1}^{n_1} v^Tx_i =v^T \frac{1}{n_1} \sum_{x_i=c_1}^{n_1} x_i = v^T\mu_1$ 
where $x_i$ is datapoint

