
Open Set - Probe identity may not be available in the gallery, so system should label unknown
Closed Set - It will be available, system should find closest one

Face Verification like face unlock, airport verification is done on open set

## FR Challenges

- Potentially low number of examples for training
- Potentially High number of unknown identities
- High Degree of similarity between individual faces
- High Degree of variability in appearance of same individual


## Inter Personal Factors (Intrinsic)

- Expression
- Ageing can cause wide variation

## Intra Personal Factors (Extrinsic)

- Pose
- Facial Paraphernalia (Camera angle, facial hair)
- Illumination


## Constrained FR

Early FR dataset contains only:
- Centred Frontal Views
- Limited pose/expression changes
- Constant Illumination

System performance not consistent with conditions:
- Varying Illumination
- Change in Pose

Applications that can use constrained conditions:
- Access Control

## Unconstrained FR

Faces need to be detected under variation
- Scale
- Pose
- Illumination
- Expression
- Occlusion

## Facial Recognition Pipeline

Face Detection:
- Localise the face
- Object Detection Task

Face Alignment:
- Face aligned to forward view using facial landmarks as they can be in any scale. 
- Specialised Face Detection is required

Face Representation:
- Converted to more discriminative representation
- May be dimension reducing transformation such as Principal Component Analysis

Face Recognition:
- Classifier for eg, KNN or sometimes complex one



