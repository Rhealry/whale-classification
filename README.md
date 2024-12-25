Whale Sound Classification Project

This project focuses on classifying whale sounds from different species using machine learning techniques. Initially, the goal was to understand the basic patterns within a single whale audio sample. This descriptive analysis provided valuable insights into the structure of whale vocalizations. Building on this foundational analysis, we further explored the sounds of three whale species using randomly sampled data from the Watkins Marine Mammal Sound Database. Specifically, we downloaded 20 audio samples each of humpback whales, bowhead whales, and fin whales to train a model for recognizing and classifying whale species based on their unique vocal characteristics.

Table of Contents
1. Project Overview
2. Data Sources
3. Setup Instructions
4. Project Structure
5. Methods
6. Results
7. Future Work
8. Acknowledgments

---

Project Overview

This project began with an in-depth analysis of a single whale sound sample to identify key features, frequency distribution, and descriptive statistics. Using these initial findings, we extended the project to a broader analysis. We randomly sampled 20 audio files each of humpback, bowhead, and fin whales from the Watkins Marine Mammal Sound Database. These samples were selected to provide a diverse dataset for training a whale sound classification model.

Our aim is to explore species-specific vocal patterns and develop a machine learning model capable of recognizing and classifying different whale species. Additionally, the project holds promise for creating accessibility solutions, such as converting whale sounds into tactile feedback for the hearing-impaired, especially using low-frequency audio characteristics.

Data Sources

The primary data comes from the Watkins Marine Mammal Sound Database. The database includes various marine mammals' vocalizations, including whales, dolphins, and seals. For this project, we focus on:
- Humpback Whales
- Bowhead Whales
- Fin Whales

We randomly selected 20 recordings for each species, specifically chosen for their low-frequency characteristics suitable for tactile feedback applications and vocalization analysis.

Setup Instructions

Prerequisites:
Ensure you have Python 3.7+ and the following libraries installed:
	pip install librosa matplotlib numpy pandas joblib scikit-learn


Data Preparation:
- Download the whale sound data as whale_sounds.zip and unzip it into the audio/ directory.
- Ensure your directory structure matches:
```
whale-sound-classification/
├── audio/
│   └── [species]/
│       └── [audio files]
├── new_audio_samples/
├── whale_features.csv
└── README.md
```
Running the Notebook:
- Open and run the provided Jupyter notebook to preprocess the audio data, extract features, and train the classification model.
- The saved model (trained_rf_model.joblib) and scaler (scaler.joblib) can be used to test new samples in the new_audio_samples/ folder.

Project Structure
```
whale-sound-classification/
├── audio/                   # Contains unzipped whale audio data by species
├── new_audio_samples/       # For testing the model on unseen audio samples
├── whale_features.csv       # Preprocessed features of whale sounds
├── README.md                # Project description and instructions
└── whale_classification.ipynb # Main project notebook
```
Methods

1. Initial Descriptive Analysis:
   - We began by analyzing a single whale audio file, performing descriptive statistics and visualization to understand its frequency distribution, MFCC characteristics, and amplitude variations.

2. Data Collection and Preprocessing:
   - Following initial analysis, we randomly sampled 20 audio recordings each of humpback whales, bowhead whales, and fin whales.
   - Applied preprocessing steps like silence removal and resampling for standardized audio quality.

3. Feature Extraction:
   - Extracted MFCC (Mel-Frequency Cepstral Coefficients) features from each audio sample, capturing the unique spectral characteristics of each species.

4. Clustering and Classification:
   - Used KMeans clustering to identify patterns within the audio features, grouping samples based on spectral similarities.
   - Trained a Random Forest classifier on the dataset to predict species based on MFCC features.

Results

- Single Audio Sample Analysis: Initial descriptive analysis provided a baseline understanding of whale sound features, which guided feature selection and preprocessing methods.
- Clustering: Unsupervised clustering showed distinct groupings corresponding to species, validating that each species has unique vocalization patterns.
- Classification Accuracy: The Random Forest classifier achieved high accuracy on the test data, demonstrating that the model generalizes well for new samples.
- Visualization: Plots of MFCC means and standard deviations highlighted significant inter-species differences in vocal characteristics, especially in low-frequency ranges.

Future Work

1. Accessibility Applications: This work can inform the design of tactile feedback systems for hearing-impaired users, allowing them to "feel" whale sounds through low-frequency vibrations.
2. Extended Species Coverage: Further research could involve additional whale species or incorporate environmental data to improve model robustness.
3. Advanced Modeling Techniques: Exploring deep learning models (e.g., CNNs) could capture more complex patterns in whale sounds.

Acknowledgments

Thanks to the Watkins Marine Mammal Sound Database for the valuable audio data, and to Victoria Evans for her guidance on focusing on low-frequency whale species. This project also aligns with the University of Edinburgh’s guidelines on ethical AI use.
