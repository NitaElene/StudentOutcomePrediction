# Student Outcome Prediction

## Overview

This project develops a unified classification system to predict a student's academic status as `Graduate`, `Dropout`, or `Enrolled`. It integrates predictions from three pre-trained binary logistic regression models: one distinguishing `Graduate` from `Dropout`, one distinguishing `Graduate` from `Enrolled`, and one distinguishing `Dropout` from `Enrolled`. The system combines these outputs using methods such as majority voting, confidence scoring, and stacking with meta-classifiers (including K-Nearest Neighbors and Decision Trees trained on meta-features derived from the base models' probabilities).

The final predictions for the test data are generated and saved in `predictions.json` via a function that selects the method (majority vote, confidence scores, or stacking).

## Data and Models

- Training data: `train_data.csv` (includes features and target labels).
- Test data: `test_data.csv` (features only).
- Answer data: `test_data_ans.csv`
- Models: `models.pickle` (dictionary of the three logistic regression models).

## Implementation

The project uses Python version 3.14.0. First, please create a virtual environment with: `python -m venv sop_venv`.

All code, including data loading, model integration methods, training of meta-classifiers, evaluation, and generation of `predictions.json`, is contained in `student_outcome_prediction.ipynb`.

To generate predictions, run the notebook and call `generate_predictions(method=3)` (where `method=3` uses the stacking approach).