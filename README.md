# FER-2013-Facial-Expresion-Classification

This project uses deep learning to classify facial expressions from grayscale face images in the FER-2013 dataset.

The notebook works as both code and the written report for the assigment. It includes data understanding, data preperation, CNN model training, model comparison, evaluation, predictions on new images, result analysis and reflection.

## Project Goal

The goal of this project is to build a convolutional neural network that can classify facial expressions from image data.

The project also shows an iterative deep learning workflow where several CNN models are tested and improved step by step.

## Project structure

Main files and folders:

- `data/` - FER-2013 dataset including train, test and own image folders
- `report_fer2013.ipynb` - notebook with code, results and written analysis
- `fer2013_model_3_optimized.keras` - saved final CNN model
- `requirements.txt` - required Python packages
- `README.md` - project information and run instructions

The `data/` folder contains:

- `data/train/` - training images divided by emotion class
- `data/test/` - test images divided by emotion class
- `data/new_images/` - own images used for prediction testing

## Dataset

The project uses the FER-2013 dataset. The dataset contains grayscale face images with a size of 48x48 pixels.

The images are divided into seven emotion classes:

- angry
- disgust
- fear
- happy
- neutral
- sad
- surprise

The dataset is already split into `train` and `test` folders. In the notebook, part of the training data is also used as validation data during model training.

## Models tested

Three CNN models were tested.

### Model 1 - Baseline CNN

A simple CNN trained on a smaller subset of the data. This was used as a first baseline to check that the full workflow worked.

### Model 2 - Improved CNN

A deeper CNN trained on the full training dataset. This model used batch normalization, dropout, data augmentation and more epochs.

### Model 3 - Optimized CNN

The final model. This model used repeated convolutional blocks, batch normalization, dropout, GlobalAveragePooling2D, careful data augmentation and learning rate scheduling.

Model 3 performed best and was saved as `fer2013_model_3_optimized.keras`.

## Final Result

The best model was Model 3.

Final test accuracy: approximately 62.9%.

The model performed best on classes such as `happy` and `surprise`.

The more difficult classes were mainly `fear` and `disgust`. This was shown in the confusion matrix and classification report in the notebook.

## Own Image Testing

The notebook also tests the trained model on two own images:

- `data/new_images/my_happy.jpg`
- `data/new_images/my_neutral.jpg`

The model predicted both own images correctly, but with lower confidence than the FER-2013 test image. This is discussed in the notebook as a limitation because own images can differ from the training data in lighting, framing, background and image quality.

## How to Run the Project

1. Clone the repository.

2. Create a virtual environment:

`python -m venv .venv`

3. Activate the virtual environment.

On Windows:

`.venv\Scripts\activate`

4. Install the required packages:

`pip install -r requirements.txt`

5. Open the notebook:

`report_fer2013.ipynb`

6. Run the notebook from top to bottom. (Results may vary)

## Saved Model

The final trained model is saved as `fer2013_model_3_optimized.keras`.

This file can be loaded later without retraining the model.