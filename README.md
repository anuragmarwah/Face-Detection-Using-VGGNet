# Face-Detection-Using-VGGNet

## Overview
This repository is for my graduate course project at NYU in the subject Introduction to Machine Learning.

Team Details: Team 1 <a href="https://github.com/anuragmarwah/Face-Detection-Using-VGGNet/blob/master/Project-Report-Team1.pdf"> (Project Report) </a>

Team Members:
  - Anurag Marwah (am8482@nyu.edu)

## Description
- I have used a pre-trained VGGNet from Keras and fine-tuned it to perform binary classification of facial data in images.
- The python <a href="https://github.com/anuragmarwah/Face-Detection-Using-VGGNet/tree/master/Code">code</a> can be described in 3 parts:
  - Download Model
  - Train Model
  - Predict Faces

### Download Model
- VGG16 is downloaded without top layer
- A new model is built on this VGGNet
- The convolutional layers are frozen so that they are not trained again
- One Flatten and Two Dense layers are added
- The result is a binary classifier

### Train Model
- The model is trained using Data Generators
- 4000 Train images and 2000 Test images are used
- Training Accuracy and Validation Accuracy are plotted

### Predict Model
- A sliding window is used to get a part of the image
- This window is passed to the image classifier trained above
- The result is 1 if there is a face in the window; 0 otherwise
- If there is a face, a box is drawn around the face
- An image pyramid is used to sub-sample the image
  - This helps in detecting faces of different sizes in the same image

## Future Scope
- Non-maximum suppression to remove the overlapping boxes
- The end result is a single box for each face in the image
