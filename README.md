# Age Prediction from Face Images (Regression)

> A neural network that estimates a person’s age from their face, with a Gradio app for uploading photos or using a webcam.

- `Live demo`: https://ab97560a99e5240d3e.gradio.live
- `code`: AGE_PRED_GA.ipynb


## Problem Statement
> The goal is to estimate a person’s age from a face image. It is a regression problem, and the model’s performance will be measured using MAE, RMSE, and R². The prediction is only an estimate and should not be used for important legal decisions.


## Dataset 
> The project uses the UTKFace dataset, which contains around 23,000 face images with ages included in the file names. Images of people older than 90 are excluded. The data is divided into 70% for training and 30% for testing.


## Preprocessing
> Images are resized to 64×64 and pixel values are scaled between 0 and 1. Sample weights are also used to reduce the bias toward the more common age groups, especially ages 20–40.

