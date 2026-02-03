# Fraud-Detection-Machine-Learning

## Project Overview
This project aims to develop an automated fraud detection system to address significant financial losses in banking. In the analyzed dataset, fraud accounts for only 0.24% of transactions but represents a total loss of €877,294.32. Given the volume of over 587,000 transactions, manual review is impossible, making machine learning a critical tool for protecting profits and optimizing the work of fraud analysts.

## Objectives
Catch at least 30% of fraudulent transactions to significantly reduce financial leakage.

Balance detection and usability by minimizing "false positives" to avoid blocking legitimate customer payments.

Efficiency: Help analysts focus on high-probability fraudulent alerts rather than manual searches.

## Methodology
The project utilizes the XGBoost algorithm, chosen for its effectiveness in handling severe class imbalances and capturing complex, non-linear relationships in transaction data.

### 1. Data Preprocessing
Feature Engineering: Extracted temporal patterns (hour and day of the week) from transaction timestamps.

Categorical Encoding: Converted qualitative variables into binary inputs using one-hot encoding (pd.get_dummies) for mathematical interpretation by the model.

Dimensionality Reduction: Removed high-cardinality identifiers like card_id and card_transaction_id to prevent overfitting.

### 2. Model Training & Validation
Data Split: 80% training set and 20% test set.

Algorithm: XGBClassifier with 100 estimators, a maximum depth of 4, and a learning rate of 0.1.

Validation: Implemented Stratified K-Fold Cross-Validation (5 folds) to ensure performance stability.

## Key Results
Average CV Recall: 49.55%.

Stability: A low standard deviation of 2.73% across validation folds.

Impact: The model successfully exceeds the initial 30% recall goal, consistently detecting nearly half of all fraudulent transactions.

## Future Considerations
The project identifies two critical steps for moving to a production environment:

Model Deployment: Transitioning the XGBoost model into a production API for real-time transaction scoring.

Model Monitoring: Tracking data drift and performance decay to ensure recall remains high as fraud tactics evolve.
