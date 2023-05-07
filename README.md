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

1. **Data collection:** Collect EEG data from subjects exposed to visual stimuli. These data were requested from Shanghai Jiao Tong University (https://bcmi.sjtu.edu.cn/home/seed/contacts.html) and they gave us access to their entire dataset of which only 4 (SEED, SEED_V, SEED-GER,SEED-FRA) are used, due to time and format.

2. **Preprocessing:** This step includes filtering the signals in different frequency bands, normalisation to adapt all signals to the same time scale and segmentation of the data of each eeg into the different stimulations Positive, Negative and Neutral.

3. **Feature extraction:** Extract relevant features from the preprocessing: signals in the different frequency bands, entropy differential (DE) and power spectral density (PSD).

4. **Feature selection:** The features selected for the emotion recognition model are taken from the article (Bands Frequencies - Position and Signals by Channels - DE - PSD): https://link.springer.com/article/10.1007/s11571-021-09751-5

5. **Model development:** In this project, two models have been created to meet the objectives. A CNN model, whose function is to recognise whether the input stimulations are POSITIVE, NEUTRAL or NEGATIVE emotions. And a GAN model, whose objective is to generate synthetic stimuli.

6. **Model training and validation:** 
   - CNN -> optimizer Adam (lr=0.0002) - loss Categorical_crossentropy
   
   - GAN (generator & discriminator) -> optimizer Adam (lr=0.0002) - loss binary_crossentropy 

7. **Evaluation:**
   - CNN -> Accuracy & loss
   
   - GAN (generator) -> Generator loss (G_loss) - Discriminator loss (D_loss) & accuracy (acc.)
   
   **Notes:**  
   G_loss: A high value indicates that the generator needs to be improved.
   
   D_loss: A low value indicates that the discriminator performs well in classifying the input data as true or false.
   
   acc.: Es la precisión del discriminador en clasificar datos de entrada que correctamente como reales o falsos.

8. **Visualization and interpretation:** For this project we have used the matplotib libraries and the libraries of the MNE library (https://mne.tools/stable/index.html). A map of the electrodes and the generated and real signals has been represented for visual comparison.

9. **Iteration and improvement:**

  - CNN -> epochs 100 - batch_size 32
  - GAN -> epochs 30 - batch_size 32
  
10. **Final Results**

## Datas

- **SEED:** EEG of 15 subjects. The data were collected while watching film clips. The videos were carefully selected to induce different types of emotions: positive, negative and neutral. https://bcmi.sjtu.edu.cn/home/seed/seed.html

- **SEED_V:** EEG of 20 subjects. Evolution of the original SEED dataset. The number of emotion categories changes to five: happy, sad, fear, disgust and neutral. https://bcmi.sjtu.edu.cn/home/seed/seed-v.html

- **SEED_GER:** EEG of 8 German subjects with positive, negative and neutral emotional labels. https://bcmi.sjtu.edu.cn/home/seed/seed-GER.html

- **SEED_FRA:** EEG of 8 French subjects with positive, negative and neutral emotional labels. https://bcmi.sjtu.edu.cn/home/seed/seed-FRA.html


## Results

metrics CNN

image GAN original & generated
metrics GAN

## Conclusions

 - CNN -> the model is very primitive and the expected accuracy value is not obtained. This is due to the structure of the model, since the article on which it is based also consists of a type of self-adaptive attention module made up of two sub-modules, the spatial attention module and the spectral attention module.

 - GAN -> As we have seen in the results, the discriminator still identifies with some accuracy those that are false and real. On the other hand, the loss of the generator can still be improved. The big problem we have encountered at this point is that the data is so large and takes up so much space in  memory to train both models. That is the reason why we have had to interpolate the time scale to 50s for each file of each stimulus (range from 52s to 300s), losing a lot of information and making it harder for the generator to find a pattern.


## Future Work

1º Improve the recognition model (CNN), understand and add the adaptive attention module in the model.

2º Test an emotion recognition model that compares the signal images for each labelled emotion.

3º Improve the GAN model trained as other input data (4D segments) or applying another method to reduce the information in a more correct way.

4º Expand the database as it is difficult to find experiments so accurate and so well stored.

5º Try to apply this methodology to other fields where it could be beneficial to recognise and generate electrical signals.

5º 

## References

- Wei-Long Zheng, and Bao-Liang Lu, Investigating Critical Frequency Bands and Channels for EEG-based Emotion Recognition with Deep Neural Networks, accepted by IEEE Transactions on Autonomous Mental Development (IEEE TAMD) 7(3): 162-175, 2015. (SEED)

- Ruo-Nan Duan, Jia-Yi Zhu and Bao-Liang Lu, Differential Entropy Feature for EEG-based Emotion Classification, Proc. of the 6th International IEEE EMBS Conference on Neural Engineering (NER). 2013: 81-84. (SEED)

- Wei Liu, Jie-Lin Qiu, Wei-Long Zheng and Bao-Liang Lu, Comparing Recognition Performance and Robustness of Multimodal Deep Learning Models for Multimodal Emotion Recognition, IEEE Transactions on Cognitive and Developmental Systems, 2021. (SEED_V)

- Wei Liu, Wei-Long Zheng, Ziyi Li, Si-Yuan Wu, Lu Gan and Bao-Liang Lu, Identifying similarities and differences in emotion recognition with EEG and eye movements among Chinese, German, and French People, Journal of Neural Engineering 19.2 (2022): 026012. (SEED-GER) (SEED-FRA)

- Schaefer A, Nils F, Sanchez X and Philippot P, Assessing the effectiveness of a large database of emotion-eliciting films: a new tool for emotion researchers, Cognition and Emotion 24.7(2010):1153-1172. (SEED-GER) (SEED-FRA)

- Neural patterns between Chinese and Germans for EEG-based emotion recognition ->https://ieeexplore.ieee.org/abstract/document/8008300

- A Long Short Term Memory Deep Learning Network for the Classification of Negative Emotions Using EEG Signals -> https://ieeexplore.ieee.org/abstract/document/9207280

- 4D Attention-based Neural Network for EEG Emotion Recognition -> https://link.springer.com/article/10.1007/s11571-021-09751-5

- Library MNE -> https://mne.tools/stable/index.html

