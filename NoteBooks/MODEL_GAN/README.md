# GAN model to create synthetic signals
This repository contains code to generate artificial EEG data using Generative Adversarial Networks (GANs).

## Overview

1. Load and preprocess real EEG data.
2. Create a GAN model, consisting of a generator and discriminator.
3. Train the GAN using real EEG data.
4. Generate artificial EEG data using the trained generator.
5. Save and visualize the generated EEG data.
6. Dependencies

## Libraries:

TensorFlow (for GAN model creation and training)
MNE (for EEG data handling and preprocessing)
NumPy, SciPy (for numerical operations)
Matplotlib, Seaborn (for data visualization)
## Results
The generated artificial EEG data is saved in two NumPy files:

generated_eeg.npy: Contains the generated EEG data in the same range as the preprocessed real EEG data.
original_range_generated_eeg.npy: Contains the generated EEG data in the same range as the original raw EEG data.
Additionally, the script visualizes the generated and real EEG data by plotting a topographic map and a time-domain plot using MNE.

