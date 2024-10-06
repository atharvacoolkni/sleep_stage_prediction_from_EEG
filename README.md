# sleep_stage_prediction_from_EEG

his project implements a deep learning model to classify different stages of sleep based on EEG data. The stages of sleep include Wake (W), light sleep (N1, N2), deep sleep (N3), and Rapid Eye Movement (REM) sleep. The data is preprocessed and modeled using Convolutional Neural Networks (CNN) and Gated Recurrent Units (GRU) for effective sequence learning.

Features:
EEG preprocessing and feature extraction
Multi-stage classification of sleep stages ( N1, N2, N3, REM ,UNKNOWN)
CNN layers for feature extraction and GRU layers for sequence modeling
Performance metrics like precision, F1-score, and accuracy to evaluate the model

Data:
The dataset consists of Polysomnography (PSG) recordings from the Sleep-EDF database. Each file contains EEG signals in .edf format and hypnograms that annotate the sleep stages.

Data source: Sleep-EDF Dataset:  https://www.physionet.org/content/sleep-edfx/1.0.0/

PSG files: EEG recordings for different individuals
Hypnogram files: Corresponding sleep stage annotations
The EEG signals were preprocessed, including standardization and segmentation into 30-second epochs. Labels for sleep stages were extracted and mapped to integers using the following mapping:

Sleep Stage	Label
Wake (W)	0
Stage N1 (Light)	1
Stage N2 (Light)	2
Stage N3 (Deep)	3
REM	4
Unknown/Artifact	5

Model Architecture
The model architecture consists of the following components:

Convolutional Layers: Extract features from the EEG data.
Batch Normalization: Normalizes activations to improve convergence.
Max Pooling Layers: Reduces the dimensionality of the data.
Dropout Layers: Prevents overfitting by randomly dropping connections.
GRU Layers: Captures sequential dependencies in the EEG time series data.
Fully Connected Layers: Final classification based on extracted features.
Output Layer: Predicts one of the 5 sleep stages using softmax activation.


Usage
Preprocessing and Data Preparation
EEG and hypnogram data are loaded using the pyEDFlib and MNE libraries.
The EEG signals are filtered, normalized, and segmented into 30-second epochs.
Sleep stage labels are extracted from the hypnogram files and mapped using predefined dictionaries.
Model Training
The CNN-GRU model is trained on the preprocessed data using the following command:


Results
After training, the model achieved the following performance metrics:

Precision: 0.7055
F1 Score: 0.6383
Accuracy: 0.7875

In an additional test using one preprocessed .pkl file, the model achieved an accuracy of:
Test Accuracy: 0.74

Conclusion
The model's performance shows promise with a precision of 0.7055, F1-score of 0.6383, and overall accuracy of 0.7875. The test results on a single .pkl file further validate the model's robustness with a test accuracy of 0.74.

Future improvements could involve experimenting with more complex architectures, tuning hyperparameters, or utilizing more EEG channels to capture additional information.
