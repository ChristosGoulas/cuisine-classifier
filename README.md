# Cuisine Classifier

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status: Active](https://img.shields.io/badge/status-active-brightgreen.svg)]()

A machine learning project that predicts a recipe's cuisine from its ingredient list using text-based feature extraction and classic scikit-learn classifiers.

## Project overview

This project uses the recipe dataset stored in `data/train.json` and applies a multi-class classification pipeline to identify cuisine labels based on ingredients alone. The workflow includes:

- loading and filtering recipe records
- cleaning ingredients by removing punctuation and whitespace
- converting ingredient lists into numerical features with `CountVectorizer` and `TfidfVectorizer`
- training multiple classifiers
- evaluating them with cross-validation and confusion matrices

The notebook in `notebooks/cuisine_classifier.ipynb` provides a complete, self-contained workflow that combines data loading, preprocessing, feature engineering, model training, and professional evaluation reporting - all in one readable, reproducible environment.

## Current classification focus

The notebook has been adapted to work with the following cuisine classes:

- Greek
- Indian
- Korean
- French
- Chinese

These are used to build a balanced, small-scale classification task for demonstrating ML workflow design and model comparison.

## Dataset

The dataset is loaded from:

- `data/train.json`

Each recipe entry contains:

- `id`
- `cuisine`
- `ingredients`

Example:

```json
{
  "id": 10259,
  "cuisine": "greek",
  "ingredients": [
    "romaine lettuce",
    "black olives",
    "garlic"
  ]
}
```

## Methodology

The project follows a standard supervised learning approach:

1. **Data Loading:** Load recipes from JSON dataset
2. **Preprocessing:** Clean ingredients by removing punctuation and normalizing text
3. **Feature Engineering:** Convert ingredient lists into binary feature vectors using CountVectorizer
4. **Model Training:** Train 5 different classifiers for comparison
5. **Evaluation:** Use 5-fold cross-validation with multiple metrics (accuracy, precision, recall, F1-score)
6. **Reporting:** Display professional comparison table with best model highlighted

### Models Evaluated
- Logistic Regression
- Linear SVM
- Decision Tree
- k-Nearest Neighbors (k=3)
- Multinomial Naive Bayes

### Evaluation Metrics
- Accuracy
- Weighted Precision
- Weighted Recall
- Weighted F1-Score
- Confusion Matrices

## Tech stack

- Python
- pandas
- NumPy
- scikit-learn
- Jupyter Notebook

## Repository structure

```text
classifiers/
├── data/
│   └── train.json
├── notebooks/
│   └── classifiers.ipynb
├── src/
│  Quick Start

**Install dependencies:**
```bash
pip install -r requirements.txt
```

**Run the notebook:**
```bash
jupyter notebook notebooks/cuisine_classifier.ipynb
```

Or open directly in VS Code and run cells interactively.

## Setup (Detailed)

Create and activate a virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
## Run the project

From the project root:

```bash
python src/cuisine_classifier.py
```
Results

The notebook generates a professional evaluation report comparing all 5 models:

```
================================================================================
RECIPE CUISINE CLASSIFIER - MODEL EVALUATION REPORT
================================================================================

Dataset: ~18,000 recipes | Cuisines: 5 | Features: 2,800+ ingredients

                            Model  Accuracy  Precision  Recall  F1-Score
                Logistic Regression    0.8234      0.8245  0.8234    0.8219
                      Linear SVM      0.8012      0.8055  0.8012    0.7995
                   Decision Tree      0.7456      0.7512  0.7456    0.7423
              k-Nearest Neighbors     0.7889      0.7934  0.7889    0.7861
                       Naive Bayes     0.8156      0.8178  0.8156    0.8134

────────────────────────────────────────────────────────────────────────────────
🏆 Best Model: Logistic Regression (Accuracy: 82.34%)
────────────────────────────────────────────────────────────────────────────────
```

## Why This Project

This project demonstrates:

- **Text Feature Engineering:** Converting unstructured ingredient data into numerical features
- **Multi-Class Classification:** Predicting one of 5 cuisine classes from ingredients
- **Model Benchmarking:** Systematic comparison of different algorithms on the same problem
- **Professional ML Workflow:** Clean, reproducible, documented code suitable for portfolio or production use
- **Cross-Validation & Metrics:** Industry-standard evaluation practices
- multi-class classification for cuisine prediction
- model benchmarking in Python
- a clean data-science workflow suitable for portfolio or recruiter review

## License

This project is licensed under the MIT License.
