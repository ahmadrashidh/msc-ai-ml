
## Canny Edge Detection
> Multi-stage edge detector

__Edge Detection using Simple kernels__:
- are sensitive to changes in intensity in an image, so they tend to find many edges and noise.
- Edges are not clearly as they are wide in pixels

__Goal of multistage detector__:

1. Localisation - finding points closer to true edge
2. Robust to noise
3. Returns single response, 1 pixel wide w.r.t to edge

## Canny Algorithm

- Canny Algorithm uses Sobel filters to perform initial edge detection and then improve it

__Steps:__

1. Apply smoothing using Gaussian
2. Sobel filtering, and two more steps to make thinner edges
3. Non-maximum suppression
4. Hysteresis Thresholding

### Non-Maximum Suppression
> NMS keeps only pixels which are local max in the direction of the gradient.(where magnitude and gradient from Sobel filtering is used)


### Hysteresis thresholding
> Determining the most important edges

- Some of the edges from Sobel filtering are false or insignificant - not denote the boundaries of the image.
- Uses two threshold levels - minVal and maxVal for pixels
- Only edges  above maxVal is retained
- Edges connected to edge of maxVal is retained

## Cons of the approach

- In some scenarios, edges produced don't describe the boundary of an object. flirts of blinds, impressions in object
- Describing edges as lines avoids issues of missing pixels.

## Hough Transform
> Enables grouping of edges into lines, using voting process.

__Goal__:
Find straight lines that intercept pixels that form edges.

$y=mx+b$

Find all candidate lines for each edge $𝑥_i , 𝑦_i$ in image space. Points in parameter space with most votes (intercepts) defines lines with best match for edges composed of points in image space.

### Problems and Polar Representation

In Parameter space (m,b), slope m can go to infinity for vertical lines
- Parameter/polar representation ($\rho,\theta$) are bounded, preferable to use - where $\rho$ -> distance from origin, $\theta$ -> angle


Candidate lines in image space doesn't map to a line in parameter space, but sinusoidal curves

Hough transform is a brute force approach where angle $\theta$ for each point is quantised to reduce the number of candidate lines.

__Probabilistic Version of the Hough Transform__ - reducing runtime of Hough transform using random subset of points in the image


