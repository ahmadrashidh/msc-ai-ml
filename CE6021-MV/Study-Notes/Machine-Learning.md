Supervised is the formalisation of learning from examples. 

### General Supervised Learning for Computer Vision

1. Converting image to representation called feature vectors
2. Classifier trained on feature vectors
3. Trained classifier can be used on test dataset

### Supervised Learning Dataset

- Training Set ( labelled)
- Validation Set (labelled) - to know if any problem arises during validation
- Test set (unlabelled)

### Features and Representations

Features correspond to edges, corners, blobs or other regions of interest
- Feature is measurable property of phenomenon being observed
- Image features are described in descriptor vector
- In ML problems, feature vectors are raw pixels

- Improve the accuracy of classifier by make feature vectors more discriminative

#### Principle Component Analysis

- Compress the redundant image pixels in feature vectors
- Less discriminative to improve computation efficiency and accuracy

### Classifiers

-  K nearest Neighbours
- SVM
- NN

Selection of classifier is based on experience and trial and error


#### Classifier Complexity

**Terms**:

Bias: Inherent Error due to model
Variance: How much classifier changes with different data

Low complex classifiers will have high bias - as it is based on simple model and therefore decision boundary may not fit well to data - Under-fitting

High complex classifiers will have high variance - decision boundary will be very complex - Over-fitting

## Generalisation

- Ability of classifier system to perform well on unseen test data - i.e goal
