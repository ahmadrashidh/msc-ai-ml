- Well-Known Object Detection Algorithm
- Commonly used in Face Detection although can be trained to detect other objects and was used in early digital cameras
- Haar-like feature engineering to improve discrimination
- Used Boosted classifier to combine many simple classifier
- Computationally Efficient - can easily be run on embedded devices - uses Integral Image of feature Computation & Cascade Classifier to speed up detection

## Feature Detection

- Operates on Sliding Window of 24 x 24
- Feature Detector runs in each window to find edges, circles and rectangles
- Combination of detectors to find face
- Lot of computation

- Author introduced the idea of the integral image to reduce the computation on addition of pixels as feature detector dimension increases.
- With Integral image, computation of feature detector can be done by just adding 4 values

### Integral Image

Steps:

- Sum along each column of the image
- Sum along each row of the image
- Each value in integral image is equal to the sum of the values above and to the left in original image
- Also called as Summed Area Table

### Scaled/Shifted Features

- Feature detector are applied in different scale and position
- 180,000 possible features for 24x24 pixel window
- In this algorithm, number of feature detectors are pruned

## Classification
- A Feature Detector is not sufficient to predict the presence of face. It only response to whether it has an edge - considered as weak binary classifier
- Classifier to combine weak classifier.
- 180,000 reduced to approx. 6000

In Viola Jones Algorithm, the many classifiers are arranged into 38 stages. Image patch are rejected by classifier as false negative at each stage
## Summary of Viola Jones Algorithms
- Slow to train but Fast Detection
Key Ideas:
- Integral Images for fast computation of feature operators.
- Adaboost to select and combine classifiers
- Cascade of classifiers
- Labelled data is required.

