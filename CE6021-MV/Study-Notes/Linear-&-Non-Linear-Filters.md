- Linear Filters
- Image Noise
- Non-Linear Filters
- Properties of Linear Filters
- Gaussian Kernel
- Separable Convolution
- Main source of Pixel Noise.

# Linear Filter

Linear Image Processing where the value of an output pixel is a linear combination of the values of the pixels in the input pixel's neighbourhood is called Linear Filter

- In Linear Filter, kernel is convolved with image to produce output image
	L = I * H

## 2D Gaussian Kernel

- Important kernel, used as first step in many algorithms
- Doesn't produces artefacts
- Used to generate scale spaces

	$G(x,y)=[1/2 \pi\sigma^2]e^{-x^2 + y^2/2\sigma^2}$
	where $\sigma$ - standard deviation parameter that determines the width of the Gaussian distribution

- Larger $\sigma$ , wider blurring

## Gaussian Distribution

- Continuous function in x
- So we must draw samples to create a kernel for image processing
- For image processing application, use sampled approximation of the Gaussian over a finite window of n pixels
	M = 6 $\sigma$ + 1
	where M is the number of samples in the kernel window


## Separable Kernels

2D Kernel is separable if can be formed from outer-product of two 1D kernels

$uv = uv^T$

- Outer product of two 1D kernels is equivalent to convolution
- 2D Kernel is separable if its symmetric

## Separable Convolution

- Convolution with large kernels is computationally inefficient
- Computationally efficiency improved by separating the kernel into components
	$L = I * H$
	$H = H_1 * H_2^T$ 
- Convolution is commutative

## Properties of Linear Filters

__Obey superposition principles__
	$(I_1 + I_2) * H_1 = I_1 * H_1 + I_2 + H_1$
	$I_1 * H_1 + I_2 + H_1 = I * (H_1 + H_2)$
__Convolution before scaling is same as convolution after scaling__
	$kI = k(I * H_1)$
__Shift Invariance__
	If the input is shifted spatially then the output will be shifted by the same amount

__Convolution is commutative
	$I * H_1 = H_1 * I$
_Convolution is associative
	$((I * H_1)*H_2)*H_3 = I * (H_1*H_2*H_3)$

# Noise

- Most noise arise during image acquisition due to sensor electronics
### Gaussian Noise
Gaussian Probability Density function
		P(g) = $1/[\sqrt{2\pi}\sigma_n]e^{-[g-\hat{g}^2]/2\sigma^2_n}$
	where g is the intensity of the noise

### Impulse Noise
> Noise due to large impulse errors during digitisation

- Cause black and white pixels in the image, called as `Salt and Pepper` noise


## Non-Linear Filters

- Non-Linear filters don't obey superposition principles.
- NL filters useful for noise removal with edge preservation
- Examples: Median filter, Bilateral Filter


### Median filter

- Can work better than linear Mean filter
- Removes Outlier values (e.g. Salt and pepper noise)
- Preserve edges

### Bilateral Filter

- Gaussian Filter operates spatially, will blur edges
- Includes range function
- Selects pixel values that close in intensity values
- Combination of two gaussians





