# ENSEMBLE-FRAMEWORK-FOR-ANTI-INFLAMMATORY-SMALL-MOLECULE-PREDICTION
## Overview
This project develops a stacked ensemble learning framework to predict 
anti-inflammatory activity of small molecules using three molecular 
representations: 2D descriptors, Fingerprints (FP), and a Hybrid of both.

## Project Structure
ENSEMBLE_ANTI-INFLAM/ 

├── main_notebook.ipynb          # Main notebook — full pipeline

├── data/                # Raw CSV datasets (Train/Test for 2D, FP, Hybrid)

├── models/              # Saved model files (.pkl, .keras)

├── FINAL_ENSEMBLE/            # Meta-learner, config, metrics, predictions

├── plots/               # ROC, PR, and spider plots for ensemble model

└── requirements.txt     # Python dependencies

## Models Used
| Representation | Models |
|---|---|
| 2D Descriptors | RandomForest, SVM-RBF, ExtraTrees, GradientBoosting, HistGradientBoosting, AdaBoost, XGBoost, LightGBM, KNN, MLP |
| Fingerprints (FP) | Extra Trees, LightGBM, XGBoost, RandomForest, GradientBoosting, AdaBoost, LinearSVM, KNN, NaiveBayes |
| Hybrid | Extra Trees, LightGBM, XGBoost, RandomForest, HistGradientBoosting, GradientBoosting, AdaBoost, SVM-RBF, KNN, Tabular ResNet, MLP |

## Final Ensemble
A stacked meta-learner (Logistic Regression) combines representation-level 
predictions from 8 base models across 2D, FP, Hybrid, using out-of-fold (OOF) predictions to 
prevent data leakage.

## How to Run
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Open `FINAL.ipynb` in Google Colab or Jupyter
4. Mount Google Drive if using Colab and update paths accordingly
5. Run cells sequentially

## Requirements
- Python 3.9+
- See `requirements.txt` for full list

## Evaluation Results of Ensemble Model
| Metric | Value |
|---|---|
| AUROC | 0.9735 |
| Accuracy | 0.9360 |
| Sensitivity |  0.9512 |
| Specificity |  0.9209 |
| MCC | 0.8725 |
