> High-level representation that can be used for image classification or image retrieval

- Orderless
- Large scale spatial information, relative scales and orientations are discarded
- Not suitable for object detection and localisation application
- Similar to bag of words representation

## Algorithm to construct Bag of features representation

### 1. Build a visual vocabulary
> list of visually similar image patches from all the images in the database

- Detect image features and represent them with descriptors like SIFT for all the images. 
- Clustering to identify similar descriptors


### 2.Assign terms to individual images
> extracting and describing features from test image and matching descriptors with those from vocabulary

- Image can therefore be converted into a list of visual words to code words corresponding to the cluster centres
### 3. Term Vector
> Counts of each individual visual word in an image are used to form a histogram analogous to the bag of words

- Weighing can be applied to reduce effect of high frequency words
