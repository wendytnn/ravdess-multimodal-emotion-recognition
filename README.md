# Multimodal Emotion Recognition using Audio and Video

## Overview

This project implements a **multimodal artificial intelligence pipeline for emotion recognition** using both audio and video information from the **RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)** dataset.

The system combines:

* **Audio-based features** extracted from speech signals, including:

  * Mel-Frequency Cepstral Coefficients (MFCCs)
  * Spectrogram features
  * Chroma features
* **Visual features** extracted from video frames using CNN-based facial feature extraction

The extracted multimodal features are used to classify human emotions into **8 emotion categories** using machine learning and deep learning approaches.

Due to computational resource limitations, this project focuses on **female actors only** from the RAVDESS dataset. This design choice is documented throughout the analysis pipeline.

---

## Project Objectives

The main objectives of this project are:

* Build an end-to-end multimodal emotion recognition pipeline
* Extract meaningful emotional features from both speech and facial expressions
* Combine audio and visual information for improved emotion classification
* Evaluate the performance of multimodal learning compared with single-modality approaches

---

## Dataset

**Dataset:** RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)

The dataset contains audio and video recordings of actors expressing different emotional states.

### Emotion Categories

The model classifies the following 8 emotions:

* Neutral
* Calm
* Happy
* Sad
* Angry
* Fearful
* Disgust
* Surprised

### Data Selection

For computational efficiency:

* Only female actor recordings were used
* Real `.mp4` video files were processed
* Audio and video modalities were extracted from the same samples to maintain multimodal alignment

---

## Project Pipeline

The overall workflow consists of the following stages:

### 1. Data Preparation

* Load RAVDESS audio-video files
* Filter dataset samples based on selected actors
* Extract emotion labels from filenames
* Organize data for multimodal processing

### 2. Audio Feature Extraction

Audio signals are processed to extract:

* MFCC features for speech characteristics
* Spectrogram representations for frequency patterns
* Chroma features for tonal information

These features capture important emotional cues from voice patterns, such as pitch, tone, and intensity.

### 3. Video Feature Extraction

Video processing includes:

* Extracting frames from `.mp4` files
* Detecting facial regions
* Using CNN-based feature extraction to generate facial embeddings

These embeddings represent visual emotional expressions from facial movements.

### 4. Multimodal Feature Fusion

Audio and visual features are combined to create a unified representation.

The fused feature vector contains information from:

* Speech characteristics
* Facial expressions

This enables the model to make predictions using multiple sources of emotional information.

### 5. Emotion Classification

The final model predicts one of eight emotion categories based on the combined audio-video features.

---

## Technologies Used

* Python
* Jupyter Notebook
* TensorFlow / Keras
* OpenCV
* Librosa
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

---

## Repository Structure

```
ravdess-multimodal-emotion-recognition/
│
├── notebooks/
│   └── multimodal_emotion_recognition.ipynb
│
├── data/
│   └── RAVDESS dataset (not included)
│
├── models/
│   └── trained models (if available)
│
├── results/
│   ├── figures/
│   └── evaluation outputs
│
├── README.md
└── requirements.txt
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/wendytnn/ravdess-multimodal-emotion-recognition.git

cd ravdess-multimodal-emotion-recognition
```

Install required dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

1. Download the RAVDESS dataset.
2. Place the dataset in the appropriate data directory.
3. Open the Jupyter Notebook:

```bash
jupyter notebook
```

4. Run the notebook cells sequentially to:

   * preprocess the dataset
   * extract audio features
   * extract video features
   * train and evaluate the emotion recognition model

---

## Results

The model performance is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix

(Add final model results and evaluation plots here after completing experiments.)

---

## Challenges and Limitations

* Video processing requires significant computational resources
* CNN-based facial feature extraction increases processing time
* Only female actors were included due to resource constraints
* Emotion recognition remains challenging due to variations in expression intensity and speech patterns

---

## Future Improvements

Possible improvements include:

* Training with the complete RAVDESS dataset
* Using transformer-based multimodal architectures
* Applying attention mechanisms for audio-video fusion
* Increasing video frame sampling quality
* Comparing different fusion strategies

---

## Authors

**Pei Wen Tan**
Student ID: D00253240

**Ines Comeron**
Student ID: D00262824

---

## Acknowledgement

This project uses the RAVDESS dataset:

Livingstone, S. R., & Russo, F. A. (2018).
The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS).

The dataset provides valuable resources for research in emotional speech and multimodal affective computing.
