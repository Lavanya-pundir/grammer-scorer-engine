
# SHL Intern Hiring Assessment – Audio Grammar Score Prediction

## Overview

This repository contains a solution for the SHL Intern Hiring Assessment 2025. The goal of the task is to **predict grammar scores** from audio recordings of participants reading or speaking.

The approach uses **MFCC audio features** and a **Random Forest Regressor** to predict the grammar scores.

---

## Dataset

The dataset consists of:

* `train/` – Training audio files (`.wav`) with labels
* `test/` – Test audio files (`.wav`) without labels
* `train.csv` – Contains `filename` and corresponding grammar `label`
* `test.csv` – Contains `filename` for which predictions are to be made

**Audio Processing:**
All audio files are resampled to **16 kHz**.

---

## Approach

1. **Feature Extraction**

   * Extracted **MFCC (Mel-frequency cepstral coefficients)** from audio files
   * Used **40 coefficients**, mean-pooled over time

2. **Model**

   * **Random Forest Regressor**
   * Trained on MFCC features to predict continuous grammar scores

3. **Evaluation**

   * **Training RMSE**
   * **Validation RMSE**

4. **Visualization**

   * Scatter plot of true vs predicted scores
   * Histogram of prediction errors

---

## Usage

Clone the repository:

```bash
git clone https://github.com/your-username/shl-audio-grammar-prediction.git
cd shl-audio-grammar-prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook SHL_Grammar_Prediction.ipynb
```

---

## File Structure

```
├── dataset/
│   ├── audios/
│   │   ├── train/
│   │   └── test/
│   ├── train.csv
│   └── test.csv
├── notebooks/
│   └── SHL_Grammar_Prediction.ipynb
├── requirements.txt
└── README.md
```

---

## Submission

The notebook produces a **submission CSV** with the following format:

| filename    | label |
| ----------- | ----- |
| audio_1.wav | 0.85  |
| audio_2.wav | 0.90  |
| ...         | ...   |

---

## Future Improvements

* Use **pre-trained audio embeddings** (e.g., wav2vec2 or HuBERT)
* Combine **text transcription features** with audio features
* Try **ensemble models** for higher accuracy

---

## Dependencies

* `numpy`
* `pandas`
* `librosa`
* `scikit-learn`
* `matplotlib`

---

## Author

**Lavanya Pundir**
SHL Intern Hiring Assessment 2025

