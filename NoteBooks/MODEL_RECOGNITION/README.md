# EEG Emotion Recognition
This repository contains code for processing and analyzing EEG signals to perform emotion recognition. The code takes advantage of various libraries such as MNE, TensorFlow, Keras, and Scikit-learn to preprocess the data, build Convolutional Neural Networks (CNNs) models, and visualize the results.

The EEG dataset used in this project is obtained from the SEED database available at the following link: https://bcmi.sjtu.edu.cn/home/seed/index.html

## Dependencies
MNE
TensorFlow
Keras
Scikit-learn
NumPy
SciPy
Matplotlib
Seaborn
Description

## The code performs the following steps:
- Import libraries and set electrode positions for visualization.
- Define frequency bands (delta, theta, alpha, beta, and gamma) and create a sparse map of zeros for further processing.
- Process the segments and create a 4D input for the CNN model.
- Preprocess the data by Winsorizing and standardizing the input.
- Create labels for each emotion (positive, neutral, and negative) and concatenate them.
- Split the data into training, validation, and testing sets.
- Define and compile the CNN model using Keras.
- Train the CNN model on the training data and evaluate its performance on the validation and testing sets.
- 
## Usage
To use this code, simply clone this repository and run the Python script. The script will process the EEG data, train the CNN model, and output the results. Make sure to have the SEED dataset downloaded and placed in the correct directory before running the script.

