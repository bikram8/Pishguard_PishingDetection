# Pishguard_PishingDetection

Code Review Summary
This Python script is designed to classify URLs into four categories: benign, defacement, phishing, and malware. It uses machine learning models (Random Forest, LightGBM, and XGBoost) to predict the type of URL based on extracted features. Below is a summary of the key components:

Key Features:
Feature Extraction:

Extracts 21 features from URLs, such as:

Presence of IP addresses.

Abnormal URL structures.

Counts of special characters (e.g., ., @, /, -, =).

URL length, hostname length, and TLD length.

Presence of suspicious keywords (e.g., "login", "bank").

Use of URL shortening services.

Data Preprocessing:

Encodes the target variable (type) into numerical labels using LabelEncoder.

Splits the dataset into training and testing sets with stratification to maintain class distribution.

Machine Learning Models:

Random Forest: Achieves high accuracy and provides feature importance.

LightGBM: Efficient for large datasets and performs well with categorical features.

XGBoost: Robust and scalable, suitable for imbalanced datasets.

Evaluation:

Uses metrics like accuracy, precision, recall, and F1-score to evaluate model performance.

Generates confusion matrices and feature importance plots for better interpretability.

Prediction:

A main() function extracts features from a given URL.

A get_prediction_from_url() function predicts the URL type using the trained LightGBM model.

Strengths:
Comprehensive feature extraction covering various aspects of URL structure and content.

Support for multiple machine learning models for comparison.

Detailed evaluation metrics and visualizations for model performance.

Areas for Improvement:
Error handling for invalid URLs or edge cases during feature extraction.

Cross-validation to ensure model robustness.

Hyperparameter tuning for better model performance.

Deployment-ready code (e.g., using Flask/Django for a web interface).

Usage:
The script can be used to classify URLs as safe or malicious.

It is suitable for cybersecurity applications, such as phishing detection or malware prevention.

Dependencies:
Python libraries: pandas, numpy, scikit-learn, lightgbm, xgboost, seaborn, matplotlib, tld, re, urllib.

Example:
python
Copy
urls = ['titaniumcorporate.co.za', 'en.wikipedia.org/wiki/North_Dakota']
for url in urls:
    print(f"URL: {url} -> Prediction: {get_prediction_from_url(url)}")
This summary provides an overview of the code's functionality, strengths, and areas for improvement, making it easy for users to understand and utilize your project.
