# Image Segmentation
> Partitioning of an image into multiple parts or regions

1. Separating background from foreground object
2. Grouping regions of similar pixels
3. Regions having semantic meaning

__Segmentation Techniques__: Active Contours, Clustering, Mean Shift, Focus thresholding, Split and Merge methods


## Thresholding
> converts image into binary image

- Histogram which accounts the number of individual pixel at each pixel intensity. Threshold pixel intensity was chosen from it.
- Threshold pixel intensity is set. All pixels greater than the threshold will be set to white, while others black. i.e. foreground lighter, background darker

## OTSU
> Contrary to manual thresholding, automatically finds the best threshold by trying all possible thresholds

- Selected threshold minimises the difference in standard deviation of pixels assigned to foreground and background in final binary image

## Problems with thresholding

- Though simple, it is unsatisfactory for segmentation unless combined with other techniques
- Most images unfortunately don't have histogram with an obvious threshold.
- OTSU methods tend to work only when bg and fg pixels are equal in numbers

## Segmentation of multiple objects

- If we apply Thresholding to a set of multiple touching similar objects, they are interpreted as one single connected object. 
Rescue is Watershed Algorithm, Split & merge method

## Watershed Algorithm

- Greyscale image
- Regions are classified based on depth of the region. 
	High values - hills - white pixels
	Low values - valleys - black pixels
	others - variation of grey

### Disadvantages

- Over-segments - small unimportant regions becomes segmented
- To mitigate this, use markers to select which local minima.

## Graph based split and merge

- Each graph vertex corresponds to an image pixel
- Assign each vertex a colour depending on which region it belongs

Determine if there should be boundary between pixels
1. Difference between regions is minimum weight edge connecting two regions. 
2. Internal difference of a regions is largest weight in the minimum spanning tree.

### Algorithm
1. Sort 𝑚 edges in increasing order of size. 
2. Allocate each pixel to it’s own region. 
3. For 𝑞 = 1, … , 𝑚
	1. Consider 𝑞 𝑡ℎ edge connecting vertices 𝑣𝑖 , 𝑣𝑗 
	2. If the vertices are in different regions then 
	3. Compute dissimilarity 
	4. If regions are not dissimilar 
	5. Merge regions



