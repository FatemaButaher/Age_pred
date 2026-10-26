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


## Model
> The model uses a simple dense network with batch normalization and random flipping to improve training. It has several dense layers and one output neuron to predict age.
> - `Loss`: MAE, the same metric used to evaluate the predictions.
> - `Optimizer`: Adam.
> - `Callbacks`: EarlyStopping to keep the best weights and ModelCheckpoint to save the best model based on val_mae.


## Results (test set)
| Metric | Value |
|---|---|
| MAE | 8.73 years |
| RMSE | 12.99 years |
| R² | 56.6% |


## Limitations and ethics
> - The model works best with clear, front-facing images. Poor lighting and face coverings may affect its predictions.
> - The dataset is not balanced across all age groups, genders, and ethnicities, which may lead to different prediction errors.
> - There are fewer images of children under 5 and adults over 70, so predictions for these ages may be less accurate.
> - Dense layers do not capture image details as well as CNNs, which may improve performance.
> - The model should not be used for surveillance, hiring, or legal age verification. Face images should also be handled with care to protect privacy.
