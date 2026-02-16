# Unsupervised Medical Anomaly Detection (Breast Cancer) 🧬

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![PyOD](https://img.shields.io/badge/PyOD-Anomaly%20Detection-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Data%20Mining-green)

## 📋 Project Overview
This project implements an **Unsupervised Anomaly Detection** system to identify malignant cases in the Breast Cancer Wisconsin dataset. Unlike traditional classification, the models identify cancer cells purely as statistical outliers, without relying on labeled training data during the learning phase.

## 🧠 Methods Used
The project utilizes the **PyOD** (Python Outlier Detection) framework to implement and compare:

1.  **kNN (k-Nearest Neighbors):** Distance-based detection. Checks the distance to the $k$-th nearest neighbor. Points far from others are anomalies.
2.  **ABOD (Angle-Based Outlier Detection):** Probabilistic method. Assesses the variance of angles between a point and its neighbors. Low variance indicates an outlier (isolated point).

## 🛠️ Pipeline
1.  **Data Loading:** UCI Breast Cancer Wisconsin (Diagnostic) Data Set.
2.  **Preprocessing:** Dimensionality handling and **StandardScaler** normalization (critical for distance-based methods).
3.  **Modeling:** Training unsupervised models with a contamination factor of 0.15.
4.  **Evaluation:**
    * **Silhouette Coefficient:** To measure cluster separation.
    * **Confusion Matrix:** Comparing unsupervised clusters against ground truth labels (Benign vs Malignant).
5.  **Visualization:** PCA (Principal Component Analysis) to project the 30-dimensional data into 2D for visual inspection of decision boundaries.

## 📊 Results
| Model | Detected Anomalies (TP) | Precision Note |
| :--- | :---: | :--- |
| **ABOD** | **65 / 212** | Higher sensitivity for sparse anomalies. |
| **KNN** | 51 / 212 | More conservative, better cluster cohesion. |

## 📦 Usage
1. Install dependencies:
```bash
pip install -r requirements.txt
