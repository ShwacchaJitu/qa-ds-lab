Bug/Defect Predictor

## Overview
A machine learning model that predicts whether a software module
is likely to contain defects, based on code metrics and historical data.

## Problem Statement
Can we predict which parts of a codebase are most likely to have bugs
before testing even begins?

## Dataset
- Source: Kaggle - Software Defect Prediction Dataset
- 60,000 software modules
- 22 features per module
- Target: defect (1 = defective, 0 = clean)
- Class distribution: 97% defective, 3% clean

## Key Findings
1. past_defects is the strongest predictor (69% feature importance)
2. static_analysis_warnings is second (22% importance)
3. cyclomatic_complexity is third (9% importance)
4. 100% accuracy on Decision Tree was identified as overfitting
5. Logistic Regression chosen as most trustworthy model

## Model Results
| Model | Accuracy | Overfit Risk |
|---|---|---|
| Logistic Regression | 93.29% | Low |
| Decision Tree depth=10 | 100.00% | High |
| Decision Tree depth=5 | 100.00% | High |
| Decision Tree depth=3 | 98.67% | Medium |

## Best Model
Logistic Regression with class_weight='balanced'
- Defect Recall: 93%
- Chosen for lowest overfit risk and honest generalization

## Tech Stack
- Python 3.13
- pandas, numpy
- scikit-learn
- matplotlib, seaborn

## Project Structure
- `data/` - Raw dataset
- `notebooks/` - Analysis and model building
- `src/` - Reusable scripts
- `outputs/figures/` - All generated charts
- `outputs/models/` - Saved model and scaler

## Key Lessons
- High accuracy does not always mean a good model
- Class imbalance must be handled before training
- Always question results that seem too perfect
- Feature importance reveals what truly matters

## Status
Complete