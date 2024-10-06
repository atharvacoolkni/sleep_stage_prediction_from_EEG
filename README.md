# sleep_stage_prediction_from_EEG

This project uses a deep learning model (CNN-GRU) to classify sleep stages from EEG data. The stages include Wake (W), light sleep (N1, N2), deep sleep (N3), and REM sleep. The model is trained on the Sleep-EDF dataset, and it uses CNN layers for feature extraction and GRU layers for sequence modeling.

Data
The dataset is from the Sleep-EDF Dataset, consisting of EEG recordings in .edf format and hypnograms for sleep stage annotations. EEG data is processed into 30-second epochs, and sleep stages are mapped to corresponding labels.

data:https://www.physionet.org/content/sleep-edfx/1.0.0/

Model
The model consists of:

CNN layers: For feature extraction.
GRU layers: For capturing sequential dependencies.
Fully connected layers: For final classification.
The model is trained using TensorFlow, with learning rate scheduling and checkpointing.

Results
Performance on the dataset:

Precision: 0.7055
F1 Score: 0.6383
Accuracy: 0.7875
Test Accuracy (using a single .pkl file): 0.74

Conclusion
The model's performance shows promise with a precision of 0.7055, F1-score of 0.6383, and overall accuracy of 0.7875. The test results on a single .pkl file further validate the model's robustness with a test accuracy of 0.74.

Future improvements could involve experimenting with more complex architectures, tuning hyperparameters, or utilizing more EEG channels to capture additional information.
