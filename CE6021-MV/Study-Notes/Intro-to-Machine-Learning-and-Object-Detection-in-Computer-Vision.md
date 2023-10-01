
## Sliding Window Object Detection

- Simple Solution to Object Detection
- Train a detector to binary classify specify object and label everything else as background
- Use some representation to convert images to feature vectors before to sending them to classifier
- Trained on image patches of specific size
- Size of Image patches = Size of sliding window

#### Cons
- Computationally inefficient
- Only use for simple detectors
- Only detects objects at one fixed scale

## Image Pyramid for scale

Because Sliding Window Object Detection is done at fixed scale, this may not detect smaller objects. So, Gaussian Image Pyramid is used which is nothing but, image is scaled into various sizes. Sliding Window detections is done on every image in Image Pyramid

## Object Detection Metrics

Intersection over Union = area(bp intersection bg) / area(bp intersection bg)

bp - predicted bounding box
bg - ground truth bounding box

Valid Detection - IoU > 30%

## Example Sliding Window Algorithms

### Viola Jones Algorithms
- Face Detection
- Cascade of weak classifiers based on simple features
- Efficient

### Histogram of Orientated Gradients
- Pedestrian Detection
- SIFT like gradient based descriptor and SVM Classifier
- Finds pattern of edges corresponding to pedestrians

