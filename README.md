# eeg-seizure-prediction
# 🧠 EEG Epileptic Seizure Prediction System

![EEG Visualization](https://example.com/eeg-banner.jpg)  
*Machine Learning Pipeline for Early Seizure Detection - CHB-MIT Dataset Implementation*

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Methodology](#-methodology)
- [Results](#-results)
- [How to Contribute](#-how-to-contribute)


---

## 🔍 Overview
**Objective**: Detect pre-seizure states from EEG signals using a 3-stage pipeline:  
1. Signal preprocessing & segmentation
2. Temporal/spectral feature extraction
3. SVM-based classification

**Key Features**:

✔️ Bandpass filtering (0.5-40Hz Butterworth)  
✔️ 2-second sliding window processing  
✔️ 23+ features per channel (statistical/spectral)  
✔️ 90.6% overall accuracy  

**Dataset**: [CHB-MIT Scalp EEG](https://physionet.org/content/chbmit/1.0.0/) (Patient chb01)

---

## 🧠 Methodology

#1. Data Processing
Filtering: 4th-order Butterworth bandpass (0.5-40Hz)

Segmentation: 2-second non-overlapping windows

Annotation: Label propagation from .seizures files

#2. Feature Extraction
Feature Type	Examples
Temporal	Mean, Variance, Skewness
Spectral	Delta/Theta/Alpha/Beta/Gamma
Non-linear	Shannon Entropy, Kurtosis
#3. Modeling
Classifier: SVM-RBF (C=1, γ='scale')

Validation: Stratified 80/20 split

Normalization: StandardScaler

##📊 Results
Class	Precision	Recall	F1-Score	Support
Interictal	0.91	1.00	0.95	13,176
Preictal	1.00	0.00	0.00	986
Ictal	1.00	0.48	0.65	44
Postictal	1.00	0.09	0.16	393
Current Limitations:
⚠️ High false-negative rate for preictal/ictal states
⚠️ Single-patient training (chb01)

##🤝 How to Contribute
Multi-Patient Training: Extend to full CHB-MIT dataset

Model Improvements:

Try LSTM/Transformer architectures

Implement class rebalancing (SMOTE)

Real-Time Features:

Live EEG visualization

Alert system integration
