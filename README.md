# EEG Motor Imagery Classification

A systematic comparison of four deep learning architectures for three-class 
EEG motor imagery classification using the PhysioNet dataset.

## Overview
This project compares Vanilla RNN, LSTM, CNN, and Transformer models on the 
PhysioNet EEG Motor Movement/Imagery Dataset (109 subjects). A strict 
subject-wise train/validation/test split is enforced to prevent data leakage.

## Models
- Vanilla RNN
- LSTM
- CNN (1D convolutional)
- Transformer with positional encoding

## Dataset
PhysioNet EEG Motor Movement/Imagery Dataset
- 109 subjects, 6 runs each
- 3 classes: Rest (T0), Left Hand (T1), Right Hand (T2)
- Electrodes: C3, Cz, C4
- Beta band: 13-30 Hz

## Key Results
| Model | Best Acc | Mean Acc |
|-------|----------|----------|
| Transformer | 43.21% | 38.38% |
| CNN | 43.00% | 41.23% |
| LSTM | 42.08% | 39.14% |
| Vanilla RNN | 41.60% | 37.87% |

CNN achieved the highest mean accuracy and most consistent performance.
Transformer achieved the highest peak accuracy but highest variance.

## Requirements
```
pip install mne torch numpy matplotlib scikit-learn scipy tqdm gdown
```

## Usage
Run the notebook cells in order. Raw data and features are loaded from 
Google Drive via gdown. GPU recommended (tested on Kaggle P100).

## Paper
Full report available in the repository as a PDF.

## Note
Results may vary slightly between runs due to stochastic subject-wise 
splitting. See notebook for details.
