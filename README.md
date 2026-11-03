# Music Genre Classification

**Machine Learning and Deep Learning for Audio Classification**

## Overview

This project explores music genre classification using the GTZAN Genre Collection dataset. Five machine learning and deep learning approaches are compared to investigate how different audio representations and model architectures affect classification performance.

The following models were implemented:

- Logistic Regression
- Support Vector Machine (SVM)
- FCNN using log-Mel spectrograms
- FCNN using 93 handcrafted audio features
- Hybrid CNN + FCNN model

Audio recordings were represented using log-Mel spectrograms and 93 extracted audio features.

The dataset was divided into training (70%), validation (15%), and testing (15%) sets using stratified sampling.

## Results

| Model | Test Accuracy |
|---|---:|
| Logistic Regression | 48.67% |
| SVM (RBF) | 50.67% |
| FCNN (Log-Mel Spectrograms) | 54.67% |
| **FCNN (93 Audio Features)** | **76.67%** |
| CNN + FCNN | 72.00% |

The FCNN trained on 93 handcrafted audio features achieved the highest reported test accuracy, outperforming the more complex hybrid CNN + FCNN architecture.

The hybrid model showed signs of overfitting, with training accuracy approaching 100% while validation accuracy remained below 80%. This suggests that the additional model complexity did not translate into better generalization on this dataset.

The results highlight the importance of feature representation, particularly when working with limited training data.

## Dataset

The project uses the **GTZAN Genre Collection**, consisting of 10 music genres:

- Blues
- Classical
- Country
- Disco
- Hip-Hop
- Jazz
- Metal
- Pop
- Reggae
- Rock

The original dataset contains 1,000 audio recordings, with 100 recordings per genre. One unreadable file was excluded during preprocessing, leaving **999 usable recordings**.

The dataset is not included in this repository due to its size.

## Installation and Usage

Install the required dependencies:

```bash
pip install -r requirements.txt
```

The project is implemented in a Jupyter Notebook:

`01_music_genre_classification.ipynb`

Download the GTZAN dataset and place it in the following directory:

```text
Data/genres_original/
```

Open the notebook and execute the cells sequentially to reproduce the preprocessing, training, and evaluation.

## Saved Models

The trained models and preprocessing scalers are saved in `.pkl` and `.pth` formats.

```text
logistic_model.pkl
svm_model.pkl
spectrogram_scaler.pkl
features_scaler.pkl
fcnn_model.pth
fcnn_93_features_model.pth
cnn_fcnn_model.pth
```

## References

- Albert Pun, Kamilla Nazirhanova — *Music Genre Classification with Mel Spectrograms and CNN*
- George Tzanetakis, Perry Cook — *Musical Genre Classification of Audio Signals*
