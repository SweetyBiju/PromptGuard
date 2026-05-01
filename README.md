# PromptGuard

PromptGuard is a machine learning project designed to detect malicious prompts and prompt injection attempts. This repository contains the code and methodology for building a robust prompt classification model to enhance AI security.

## Objective
The primary objective of this project is to develop a binary classification model that can accurately distinguish between benign and malicious prompts. By identifying structural anomalies, syntactic irregularities, and common prompt injection heuristics, PromptGuard helps secure Large Language Models (LLMs) against jailbreaks and adversarial inputs.

## Dataset
The project utilizes a dataset comprising prompts and their corresponding labels (Benign vs. Malicious). The data undergoes extensive preprocessing:
- **Flawless Text Consolidation:** Combining multiple text fields (Prompt, text, question1, question2) to prevent data loss.
- **Handling Missing Values:** Dropping records with missing target labels and securely imputing missing numerical values (e.g., Length, Perplexity).

## Feature Engineering
We engineered several domain-specific features to capture the nuances of malicious prompts:
- **Length Metrics:** `char_count` and `word_count` to analyze prompt verbosity.
- **Syntactic Anomalies:** `special_char_ratio` to detect an unusual abundance of special characters (e.g., `<<<`, `{}`, `\n`) frequently used by attackers.
- **Jailbreak Heuristics:** `injection_keyword_count` leveraging a predefined set of adversarial keywords (e.g., 'ignore', 'bypass', 'override', 'pretend').

## Exploratory Data Analysis (EDA)
Comprehensive EDA was conducted to understand feature distributions and relationships:
- **Class Distribution Analysis:** Visualizing the balance between malicious and benign samples.
- **Point-Biserial Correlation:** Identifying the continuous features that have the strongest correlation with the binary target variable.
- **Density Plots:** Examining the distribution of engineered features, such as the `special_char_ratio`, across different classes.

## Implementation & Requirements
The project is implemented in Python. Key libraries include:
- `pandas` for data manipulation
- `numpy` for numerical operations
- `matplotlib` & `seaborn` for data visualization
- `scipy` for statistical analysis

## Future Work
- Implementation and evaluation of baseline machine learning models (e.g., Logistic Regression, Random Forest, XGBoost).
- Hyperparameter tuning to optimize classification metrics.
- Advanced NLP techniques including embeddings and deep learning approaches for improved text classification.
