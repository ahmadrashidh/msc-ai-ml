- Sampling and Aliasing
- Cause of Aliasing
- How changing size of images involves interpolation of images
- Resampling and how aliasing rise in this as well

# Sampling
> Digital images are captured by the process of sampling

## 1D Signal Processing

Key Theorem in Signal Processing - [[Nyquist Shannon Sampling Theorem]]

In Image processing, frequency information is measured as the change in pixel intensity across the image.

Low frequency - Low pixel intensity(ex: Sky)
High Frequency - rapid changes in intensity / repeating patterns (ex: brickwork)

# Aliasing 
> Appearance of new frequencies in the process of sampling

- Observed in high frequency information



# Reconstruction of signals
> From digital samples to continuous signals

- The process can be said as filling in all missing sample to form continuous signal - using Interpolation filter
- Can we achieve perfect reconstruction? [[Whittaker-Shannon Interpolation Formula]]

## Practical 1D Interpolation Filters

### Replication
> Replicates samples to fill in missing signals

- Implemented as convolution operation - Box Function
### Linear Interpolation
> Missing points are formed as linear interpolation of samples

- Implemented as convolution operation - Triangle Function

Less effective at removing image frequencies


## Signal Resampling
> Used to change sample rate of signal

- Reconstructing signal and selecting new set of samples from them.
- Aliasing can arise.

# Image resizing
> Resizing images is equivalent to changing sample rate of images.

- 2D interpolation applied to reconstructing signals at new locations, so aliasing can occur

__Interpolation methods for images__
1. Nearest Neighbours
2. Bi-linear interpolation(4 points)
3. Bi-cubic interpolation(16 points, expensive)
4. Sinc

Aliasing worses on reducing image size


### Bilinear Interpolation

- Intensity at new pixels is obtained as linear combination of original pixels. More closer pixels contributes more.(in a geometric view)


### Gibbs phenomenon 
> Phenomena behind ripple effect in reconstructed image using Sinc filter

- Caused due to ringing response to the edge in image due to truncation of Sinc kernel



