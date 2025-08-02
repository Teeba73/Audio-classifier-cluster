# Audio-classifier-cluster
The provided audio clips will be classified as either clean or noisy, followed by clustering based on their respective languages.
#  Clean vs Noisy Audio Classification

This project classifies audio clips into **Clean** or **Noisy** using MFCC features, Voice Activity Detection (VAD), and an XGBoost classifier.

---

##  Dataset

- **Source:** [Common Voice Dataset](https://commonvoice.mozilla.org/en/datasets)  
- **Version:** `cv-corpus-19.0-delta-2024-09-13`
- 
---

##  Features

- Automatic extraction of `.tar.gz` dataset  
- Filtering clips using **Voice Activity Detection (VAD)**  
- Computing **Signal-to-Noise Ratio (SNR)** to label clips as clean or noisy  
- Extracting MFCC, delta, and delta-delta features  
- Training an **XGBoost** classifier  
- Evaluating with accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrix

---


## Model Details

Algorithm: XGBoost Classifier
Features: 39-dimensional vector (13 MFCC + delta + delta-delta)
SNR threshold: 15 dB for labeling clean vs noisy


## How It Works

Extract dataset from .tar.gz file
Use VAD to verify presence of human speech
Calculate SNR and label clips:
0 = Clean if SNR ≥ 15 dB
1 = Noisy if SNR < 15 dB
Extract MFCC + delta + delta-delta features
Train an XGBoost classifier
Evaluate and print classification metrics


##  Requirements

Install dependencies with:
```bash
pip install -r requirements.txt
```

###  Notes

Make sure your .tar.gz dataset file is complete and not corrupted.
The script processes only the English (en) subset by default. You can change this path to use other languages.
Ensure the extracted dataset folder contains both clips and validated.tsv.


