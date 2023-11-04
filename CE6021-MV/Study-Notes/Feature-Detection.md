- Concept of key-points and feature detection
- How making feature detector scale invariant is useful
- Laplacian of Gaussian scale-invariant detector
# Image Key-points

- Also knows as interest points or features
- points in the image that interesting or otherwise standout i.e. corners in design on plate
- Need to use feature detectors to find key-points

### Uses:
- Image matching
- Simple Object Detection
- Image alignment i.e. for creating panoramas
- Robot navigation

# Feature Detectors

__What makes good feature detector__
1. Local: finds local features robust to occlusion/clutter
2. Invariant: scale and rotation invariant
3. Robust: can tolerate noise and blur
4. Quantity: many features detected for small objects
5. Accurate: precise location

__Goal:__
Is to find detector that is able to find the same set of keypoints in two images of the same objects where we have scale or rotation differences.

## Feature Detector Invariance

Harris corner is not scale invariant, so cannot be used as feature detector.

## Laplacian of Gaussians (LoG) Blob Detector

- Both scale and rotation invariant
- Able to detect circular or blob like regions of image intensity at different scales.

+ LoG kernel is formed from application of the Laplacian operator onto the Gaussian kernel:

	$LoG_norm(x,y) = \frac{1}{\pi \sigma^2}(\frac{x^2 + y^2}{2\sigma_2}-1)e^-{\frac{x^2+y^2}{2\sigma^2}}$

- Series of kernels - Larger $\sigma$, wider LoG kernels. 
- Each kernel respond strongly to circular regions or blobs in images that have corresponding size to the kernel. 
- Can detect blobs at different scales in images by convolving an input image with the different size LoG kernels

### Algorithm

1. Generate series of LoG kernels at different $\sigma$ values
2. Convolve greyscale image with each of the LoG kernels
	1. For each image, obtain normalised square response.
	2. Find maxima values in this response that gives coordinates of the keypoint.
	3. Threshold set baed on what we are looking for.
	4. Mark key-points
	5. Apply Non Maximal Suppression


