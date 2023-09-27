- Linear Image Processing Processing
- 1D Convolution
- 2D Convolution
- Calculate output size after convolution

## Linear Image Processing
> Images are processed to sharpen, blur or enhance edges

- Processing is called linear as the value of output pixel is a linear combination of the values of the pixels in the input pixel's neighbourhood
- Filtering performed using Kernels

### Kernels
> Small arrays of pixels

- Represents math function or filter that is applied to an image
- It is convolved with image array to produce the output image

## 1D Convolution

- Modification of one signal by another
- Result of passing a sequence through a Linear Time Invariant System

$(x*h)[n] =\sum_{i=\infty}^\infty x[k]h[n-k]$
=> $(x*h)[n] =\sum_{i=\infty}^\infty x[k]h[-(k-n)]$
where x -> input sequence
h -> kernel
\- -> reversal
n -> Time(position) shift relative to input sequence
Positive value of n : Delayed(moved right)
Negative value of n : Advanced(moved left)

### 1D Convolution Example

$(x*h)[n] =\sum_{i=\infty}^\infty x[k]h[n-k]$
where n -> original samples of the sequence and kernel 
			-> output samples of the convolved operation
			-> delays of the kernel during convolution

The calculation process of moving kernel across sequence is called __sliding kernel__

## Cross-correlation
> If we didn't not reverse the kernel but still multiplied the time shifted kernel with the input sequence: this would be Cross-correlation


$(x*h)[n] =\sum_{i=\infty}^\infty x[k]h[n+k]$

- If the filter kernel is symmetrical $h[k] = h[-k]$, convolution and correlation is same.

## 2D Convolution
> Kernel shifted in 2 dimensions

$(x*h)[m,n] =\sum_{j=\infty}^\infty \sum_{i=\infty}^\infty x[i,j]h[-(i-m),-(j-n)]$

1. Reverse the kernel in both horizontal and vertical
2. Sliding the kernel around the image and element-wise multiplication.

## Padding

- Slide kernel to positions where kernel just overlaps image. This will create some edge effects
- Size of output image may change.
- In practice, we may choose specific number of padding, to preserve output size.

### Calculating output size of convolution operations

Three main cases:
1. __Valid Padding i.e. no padding__
	s = 1 and p = 0
	o = i - k + 1
	where i -> input image size
	k -> kernel size
	o -> output image size
	p -> padding
	s -> stride - how far kernel is moved on each step usually
2. __Same Padding__(odd size kernels only) i.e. calculate padding to have same output size
	s = 1, p = k/2
	o = i + 2(k/2) - (k-1)
3. __Full Padding__ i.e. padding such that kernel just overlaps image
	s = 1
	p = k -1
	o = i + (k-1)

