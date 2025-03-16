# Automated_Sleep_Stage_Classification_ML
This project aims to classify sleep stages using ensemble machine learning techniques on the Sleep-EDF dataset. The goal is to achieve at least 80% accuracy. The repository includes preprocessing, feature extraction, multiple ML models, and evaluation metrics.
## Data Preprocessing
Data preprocessing is essential for cleaning and transforming raw EEG signals into meaningful features. We use the Sleep-EDF dataset, which contains EEG recordings of sleep stages.

### Steps and Functions:

#### Load Sleep-EDF Dataset using mne.io.read_raw_edf()
Reads the raw EEG signal from .edf files.
Function: load_data(filepath)

#### Extract events from annotations using mne.events_from_annotations()
Converts sleep stage annotations into numerical labels.
Function: extract_events(raw_data)

#### Create 30-second epochs using mne.Epochs()
Segments EEG signals into 30-second windows for analysis.
Function: create_epochs(raw_data, events)

#### Extract features from EEG signals (mean,variance,power spectral density, etc.)
Reduces dimensionality while retaining useful information.
Function: extract_features(epoch_data)

#### Standardize data using StandardScaler
Normalizes features for better model performance.
Function: standardize_features(features)

#### Ensure balanced class distribution to avoid biased evaluation
Uses techniques like SMOTE (Synthetic Minority Over-sampling Technique).
Function: balance_classes(features, labels)
