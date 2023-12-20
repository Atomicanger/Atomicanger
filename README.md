# Stress Detection using Machine Learning

## Project Overview

This repository presents a comprehensive stress detection project utilizing machine learning models trained on the Wearable Stress Affect Dataset (WESAD). The primary objective is to predict stress levels based on physiological signals obtained from wearable devices.

### Dataset Details

#### WESAD Dataset
- **Collection**: Collected physiological and motion sensor data from 15 participants.
- **Devices Used**: RespiBAN Professional and Empatica E4 were employed for data collection.
- **Participant Demographics**: Included 12 male and 3 female individuals aged 27 ± 2.4 years. The exclusion criteria involved specific health conditions such as pregnancy, heavy smoking, mental disorders, chronic, and cardiovascular diseases.

### Experimental Protocol

#### Phases
1. **Baseline Condition**: A neutral emotional state was induced over a 20-minute period with subjects seated or standing, provided with neutral reading material.
2. **Amusement Condition**: Participants viewed eleven funny video clips with interspersed neutral sequences, lasting a total of 392 seconds.
3. **Stress Condition**: The Trier Social Stress Test (TSST) was conducted, wherein subjects were tasked with delivering a speech to a panel and performing a cognitive task, inducing stress over 10 minutes.
4. **Meditation**: A guided meditation followed the stress and amusement conditions to return participants to a close-to-neutral affective state.
5. **Recovery**: Sensors were synchronized again, removed, and participants were informed of the real nature of the research panel.

### Features Extracted

#### Signals Captured
- RespiBAN Device: ECG, EDA, EMG, TEMP, XYZ, RESPIRATION data sampled at 700Hz.
- Empatica E4: ACC, BVP, EDA, TEMP raw data.

### Data Preprocessing

#### Processed WESAD Dataset
- The dataset used in this study is a processed version of the WESAD dataset obtained from Kaggle.
- Features were extracted to derive combined Heart Rate Variability (HRV) of all subjects.

#### HRV Features

| Feature    | Description                          |
|------------|--------------------------------------|
| MEAN_RR    | Mean of RR intervals (heart rate)    |
| MEDIAN_RR  | Median of RR intervals                |
| SDRR       | Standard deviation of RR intervals    |
| ... (and more) | Detailed HRV features available in the dataset |

## Methodology

### Model Building

#### Implemented Models
1. **Logistic Regression**: Hyperparameters tuned: max_iter=1000, penalty='l2'.
2. **Random Forest**: Hyperparameters set: n_estimators=100, min_samples_split=2.
3. **K-Nearest Neighbours**: Number of neighbors: k=5.
4. **Artificial Neural Network (ANN)**:
   - Architecture: Input layer, two hidden layers, output layer with 'relu' activation for hidden layers and 'SoftMax' for output.
   - Loss function: 'sparse_categorical_crossentropy'.
   - Optimizer: 'Nadam'.
   - Metrics: 'accuracy'.
   - Training configuration: Batch size 32, epochs 30, validation split 0.2.

### Evaluation Metrics

| Model                | Accuracy | F1 Score | Precision | Recall  |
|----------------------|----------|----------|-----------|---------|
| Logistic Regression  | 75.29%   | 0.6660   | 0.7440    | 0.6491  |
| KNN                  | 99.95%   | 0.9994   | 0.9995    | 0.9993  |
| Random Forest        | 99.98%   | 0.9998   | 0.9998    | 0.9998  |
| ANN                  | 92.24%   | -        | -         | -       |

### Results and Analysis

- **Model Performance**:
  - Random Forest and KNN exhibited superior performance in predicting stress levels.
  - Logistic Regression showed comparatively lower accuracy and F1 scores.
  - ANN performed moderately, suggesting potential for further refinement or feature engineering.

## Conclusion

This project aimed to explore stress detection using machine learning models on the WESAD dataset, achieving notable accuracy using Random Forest and KNN classifiers. The dataset, methodology, and model performances are thoroughly detailed, providing insights into stress level prediction based on physiological signals.
