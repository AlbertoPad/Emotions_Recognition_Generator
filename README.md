# EMOTION RECOGNITION & CREATION OF SYNTHETIC EMOTIONS & VISUALISATION

## Abstract
The main objective of this project is to recognise positive, negative and neutral emotions from electroencephalography (EEG) data obtained from subjects exposed to visual stimulation. To achieve this goal, a convolutional neural network (CNN) model is developed to classify emotions. In addition, synthetic signals are generated using generative adversarial networks (GANs) and data interpolation to enrich the training dataset. Finally, the MNE library is used to visualise the signals and evaluate model performance.

## Context
The context of this project is centered around the development of technology for the digital transformation of thoughts and the analysis of brain signals, with potential applications in various fields. Key areas of interest include:

Transforming thoughts into a digital format, enabling a deeper understanding of the human mind and its processes.
Assessing a patient's mental state without the need for verbal communication, which could lead to more accurate diagnoses and personalized treatment plans.
Enhancing communication with artificial limbs, improving the lives of those with physical disabilities and amputations.
Enhancing virtual reality experiences in video games by integrating brain signals, creating more immersive and engaging environments.
Developing artificial stimuli to support patients with neurodegenerative diseases such as Alzheimer's and dementia, potentially slowing down the progression of these conditions and improving patients' quality of life.
The project leverages machine learning techniques, specifically deep learning and signal processing, to analyze electroencephalography (EEG) data and recognize emotions, which can further contribute to the advancement of these applications.


## Methodology

**Data collection:** Collect EEG data from subjects exposed to visual stimuli. These data were requested from Shanghai Jiao Tong University (https://bcmi.sjtu.edu.cn/home/seed/contacts.html) and they gave us access to their entire dataset of which only 4 (SEED, SEED_V, SEED-GER,SEED-FRA) are used, due to time and format.

Preprocessing: This step includes filtering the signals in different frequency bands, normalisation to adapt all signals to the same time scale and segmentation of the data of each eeg into the different stimulations Positive, Negative and Neutral.

Feature extraction: Extract relevant features from the preprocessing: signals in the different frequency bands, entropy differential and spectral power density.

Feature selection: The features selected for the emotion recognition model are taken from the article: https://link.springer.com/article/10.1007/s11571-021-09751-5

Model development: Develop a machine learning or deep learning model to classify emotions based on the selected features. Common models include Convolutional Neural Networks (CNNs), Recurrent Neural Networks (RNNs), Support Vector Machines (SVMs), and k-Nearest Neighbors (k-NN).

Model training and validation: Train the model on a dataset and validate its performance using cross-validation or other evaluation techniques. Fine-tune hyperparameters to optimize the model's performance.

Evaluation: Test the model's performance on an independent dataset to evaluate its generalization capability. Common evaluation metrics include accuracy, F1-score, precision, recall, and area under the receiver operating characteristic (ROC) curve.

Visualization and interpretation: Visualize the results using appropriate tools, such as the MNE library for EEG data, to gain insights into the model's performance and understand the underlying patterns in the data.

Iteration and improvement: Based on the evaluation and insights, iterate and improve the model as needed. This may involve refining the features, modifying the model architecture, or adjusting the training process.

By following this methodology, researchers can develop effective models for emotion recognition and analysis using EEG data, which can be applied to various practical applications as previously discussed.
## Datas

## Results

## Conclusions

## Future Work

## References
1. Wei-Long Zheng, and Bao-Liang Lu, Investigating Critical Frequency Bands and Channels for EEG-based Emotion Recognition with Deep Neural Networks, accepted by IEEE Transactions on Autonomous Mental Development (IEEE TAMD) 7(3): 162-175, 2015. (SEED)

2. Ruo-Nan Duan, Jia-Yi Zhu and Bao-Liang Lu, Differential Entropy Feature for EEG-based Emotion Classification, Proc. of the 6th International IEEE EMBS Conference on Neural Engineering (NER). 2013: 81-84. (SEED)

3. Wei Liu, Jie-Lin Qiu, Wei-Long Zheng and Bao-Liang Lu, Comparing Recognition Performance and Robustness of Multimodal Deep Learning Models for Multimodal Emotion Recognition, IEEE Transactions on Cognitive and Developmental Systems, 2021. (SEED_V)

4. Wei Liu, Wei-Long Zheng, Ziyi Li, Si-Yuan Wu, Lu Gan and Bao-Liang Lu, Identifying similarities and differences in emotion recognition with EEG and eye movements among Chinese, German, and French People, Journal of Neural Engineering 19.2 (2022): 026012. (SEED-GER) (SEED-FRA)

5. Schaefer A, Nils F, Sanchez X and Philippot P, Assessing the effectiveness of a large database of emotion-eliciting films: a new tool for emotion researchers, Cognition and Emotion 24.7(2010):1153-1172. (SEED-GER) (SEED-FRA)




 
