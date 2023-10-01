
- Simple Derivative Edge Detection
- Prewit, Sober, Laplacian, Atlassian kernels

## Edges

- Regions of different colours , intensity or texture.
- Location in image with rapid pixel variation.
- Edges can be found by detecting high rate of change of pixels.
- Can be found by derivative based filters which respond to regions of high rate of change - shows as negative and positive values

## Noise and Edge Detectors

- Edge detectors are sensitive to noise, so smooth with Gaussian to remove noise before all.

__Simple Derivative filters__ - Prewit,  Sobel, Laplacian
__Advanced__ - Canny Edge Detector

## Prewit Kernels
> 1D Central Difference Approximation

X-Directional Kernel: $$
\begin{bmatrix}  
-1 & 0 & 1\\  
-1 & 0 & 1\\
-1 & 0 & 1
\end{bmatrix}
$$
Y-Directional Kernel:
$$
\begin{bmatrix}  
1 & 1 & 1\\
0 & 0 & 0\\
-1 & -1 & -1
\end{bmatrix}
$$


One dimensional central difference for the end pixel of a function F:

$\Delta f[n]=f[n+1] - f[n-1]$

- Detect vertical edges using X-direction kernel, while horizontal edges using Y-direction kernel. They wouldn't respond vice versa

__Magnitude and Direction__

Magnitude $G_(i,j)=\sqrt{G^2_{x_{(i,j)}} + G^2_{y_{(i,j)}}}$

Direction $\theta_(i,j) = tan^-1(G_{y_{(i,j)}}/G_{x_{(i,j)}})$
where $G_{x_{(i,j)}}$ is the convolution of X-direction kernel with image , $G_{Y_{(i,j)}}$ is the convolution of Y-direction kernel with image 

__How we display image containing negative values after edge detection__?



1. Remove negative offset and scale to 0-255 8-bit range
	Falling edge - black lines
	Rising edge - White lines
2. Obtain square of pixel values, get square root and scale to 8-bit range.

## Sobel Kernels

- Two simple 3*3 kernels that detect horizontal and vertical edges in an image
- Can be decomposed Gradient and Averging part

X-Directional Kernel: $$
\begin{bmatrix}  
-1 & 0 & 1\\  
-2 & 0 & 2\\
-1 & 0 & 1
\end{bmatrix}
$$
Y-Directional Kernel:
$$
\begin{bmatrix}  
1 & 2 & 1\\
0 & 0 & 0\\
-1 & -2 & -1
\end{bmatrix}
$$
__Magnitude and Direction__

Magnitude $G_(i,j)=\sqrt{G^2_{x_{(i,j)}} + G^2_{y_{(i,j)}}}$

Direction $\theta_(i,j) = tan^-1(G_{y_{(i,j)}}/G_{x_{(i,j)}})$



## Gaussian Derivative

For Prewitt, smooth using Gaussian Kernel, so that needs 2 sequential operations:
1. Convolution with Gaussian Kernel
2. Convolution with edge detection

Instead, we can apply Gaussian derivative kernel, only 1 convolution required:

$G(x,\sigma)=[1/\sigma\sqrt{2 \pi}]e^{-x^2/2\sigma^2}$

$\frac{d}{dx}G(x,\sigma)=[e^{-x^2/2\sigma^2}x/\sigma^3 \sqrt{2 \pi}]$

## Laplacian Kernel

- Second Order Derivative
- Only one kernel for both directions, sum of second order derivatives in two directions
$\Delta^2 = \frac{d^2}{dx^2} + \frac{d^2}{dy^2}$

Kernel:
$$
\begin{bmatrix}  
0 & 1 & 0\\
1 & -4 & 1\\
0 & 1 & 0
\end{bmatrix}
$$
