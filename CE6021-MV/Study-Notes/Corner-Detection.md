
# Basic Corner Detection

Corners are:
- important features
- not affected by illumination
- rotationally invariant i.e. corners appear in the same place in an image no matter how its rotated
- extracted corners can be used for image matching and stereo vision

Corners detected by looking through a small detector window to monitor intensity changes in multiple directions
- Edge has intensity changes in one direction
- Corners has in multiple directions


## Basic Corner Detection through Window function

For image intensities 𝐼, Define 𝐸 as the change in intensity by a shift in position 𝑥, 𝑦 of the detector window.(direction quantised to 45 degrees, therefore in 8 directions)

$E_{x,y} = \sum W_{u,v}|I_{x+u,y+v} - I_{u,v}|^2$
where $w_{u,v}$ is the detector window function

Algorithm:
1. Start (next) point u,v in image
2. Find $E_{x,y}$ for set of 8 single pixel shifts
3. Corner detected when threshold is exceeded by minimum value of $E_{x,y}$

## Harris Corner Detection

Why?
- Improves basic corner detection
- Is able distinguish edges and corners, but predominantly used to find corners and reject edges
- Basic corner detector only allow pixel shifts quantised to 45 degrees while Harris enabled in all possible small shifts in any direction





