# LOAD DATA, DESCOMPOSE AND TRANSFORM FORMAT IN .FIF

This repository contains Python code for analyzing Electroencephalogram (EEG) data. The code uses several key libraries for EEG signal processing and data analysis.

## Description
The code performs the following:

1. Lists all the files in a specific directory that have the .cnt extension and stores them for processing.

2. For each .cnt file, it loads raw EEG data using the MNE library.

3. It drops channels that are not used in the analysis (specifically, 'M1', 'M2', 'VEO', 'HEO').

4. It applies a bandpass filter to the raw data to eliminate noise.

5. The raw data is divided into "trials", based on a predefined list of start and end seconds, and each trial is associated with a specific emotion ('POSITIVE', 'NEGATIVE', 'NEUTRAL').

6. For each trial, it extracts the relevant segment from the raw data and saves this segment to a .fif file. The output file is named according to the file, trial, emotion, start, and end, and is stored in the corresponding directory based on the emotion.

## Libraries Used
- mne: Used to load and process raw EEG data.
- pandas: Used for data analysis and manipulation.
- numpy: Provides support for arrays and multi-dimensional arrays along with a large collection of mathematical functions to operate on these arrays.
- os: Provides a way of using operating system-dependent functionality, like reading or writing to the file system.
- tqdm: Provides a progress bar to help track the progress of loop operations.
- re: Provides regular expression matching operations.
- time: Provides functions to work with times and dates.
- shutil: Provides high-level file and file collection operations.
- warnings: Used to ignore warnings.

## Execution
To run this code, you'll need to have Python 3 and the above libraries installed on your system. Then, you can simply clone this repository and run the Python script in your local environment.

## Warning
The code is set up to work with a specific file and data structure. If you wish to use this code for your own EEG analysis, you may need to make modifications to fit your own data and file structure. You must have access to the database and change the path.

## Performance
At the end of the script, it prints the total time it took to execute the script. This could be useful for optimizing and improving the script in the future.
