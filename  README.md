# IT Support Ticket Classification

## Project Overview

This project uses Natural Language Processing (NLP) and Machine Learning to automatically classify IT support tickets into different categories and assign a priority level.

The system takes a support ticket as input and predicts:

- Ticket Category
- Ticket Priority

## Objective

The main objective of this project is to build an automated IT support ticket classification system that can:

- Understand support ticket text
- Classify tickets into relevant categories
- Assign an appropriate priority level
- Provide predictions for new support tickets

## Dataset

The project uses an IT Service Ticket Classification dataset containing support ticket text and topic labels.

### Dataset Columns

- `Document` - Support ticket text
- `Topic_group` - Ticket category

The dataset contains approximately 47,837 support tickets.

## Input

The system accepts an IT support ticket as text.

### Example Input

```text
My laptop is not working and I cannot access the system. This is urgent.
```

## Data Cleaning

The following data cleaning steps were performed:

- Removed duplicate records
- Removed missing values
- Removed empty ticket text
- Checked dataset structure
- Checked category distribution
- Analyzed ticket text length

## Exploratory Data Analysis

EDA was performed to understand:

- Ticket category distribution
- Category percentages
- Category balance
- Ticket text length
- Category-wise text length
- Sample support tickets

A model accuracy comparison graph was also generated.

## NLP Preprocessing

The ticket text was processed using:

- Lowercase conversion
- Special character removal
- Extra whitespace removal
- Tokenization
- Stopword removal

## Feature Extraction

TF-IDF (Term Frequency-Inverse Document Frequency) was used to convert ticket text into numerical features.

### TF-IDF Configuration

- Maximum features: 10,000
- N-gram range: 1-2
- Minimum document frequency: 2
- Sublinear TF enabled

## Machine Learning Models

Three classification algorithms were evaluated:

1. Logistic Regression
2. Multinomial Naive Bayes
3. Linear Support Vector Machine (SVM)

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Classification Report
- Confusion Matrix

## Model Results

| Model | Accuracy |
|---|---:|
| Linear SVM | 85.69% |
| Logistic Regression | 85.44% |
| Naive Bayes | 77.86% |

## Best Model

Linear SVM achieved the highest accuracy of approximately **85.69%** and was selected as the final ticket category classification model.

## Priority Classification

The dataset does not contain a priority label.

Therefore, a rule-based priority classification approach was implemented using ticket text keywords.

### Priority Levels

- High
- Medium
- Low

Urgent or critical issues such as system failures, outages, security issues, and data loss are assigned higher priority.

## Prediction System

The final prediction system accepts a new IT support ticket and performs the following steps:

```text
New Support Ticket
        ↓
Text Preprocessing
        ↓
TF-IDF Transformation
        ↓
Linear SVM Classification
        ↓
Predicted Category
        ↓
Priority Classification
        ↓
Final Result
```

## Example Prediction

### Input

```text
My laptop is not working and I cannot access the system. This is urgent.
```

### Output

```text
===== SUPPORT TICKET RESULT =====

Ticket: My laptop is not working and I cannot access the system. This is urgent.

Category: Hardware
Priority: High

=================================
```

## Output

The system provides two main predictions:

- **Category:** Predicted IT support ticket category
- **Priority:** Predicted ticket priority level

The trained Linear SVM model is used for category prediction, while a rule-based approach is used for priority assignment.

## Project Structure

```text
Support_Ticket_Classification/
│
├── data/
│   ├── all_tickets_processed_improved_v3.csv
│   ├── cleaned_support_tickets.csv
│   ├── preprocessed_support_tickets.csv
│   └── final_support_tickets.csv
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda_and_analysis.ipynb
│   ├── 03_nlp_preprocessing.ipynb
│   ├── 04_category_classification.ipynb
│   ├── 05_priority_classification.ipynb
│   └── 06_prediction_demo.ipynb
│
├── models/
│   ├── linear_svm_ticket_classifier.pkl
│   └── tfidf_vectorizer.pkl
│
├── outputs/
│   ├── graphs/
│   │   └── model_accuracy_comparison.png
│   ├── confusion_matrix/
│   │   └── linear_svm_confusion_matrix.csv
│   └── model_results/
│       └── category_model_comparison.csv
│
├── README.md
└── requirements.txt
```

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NLTK
- Matplotlib
- Seaborn
- Joblib
- Jupyter Notebook

## Key Results

- Successfully processed approximately 47,837 IT support tickets.
- Performed NLP-based text preprocessing.
- Converted ticket text into numerical features using TF-IDF.
- Trained and evaluated three machine learning models.
- Linear SVM achieved the highest accuracy of **85.69%**.
- Generated a confusion matrix for model evaluation.
- Saved the trained Linear SVM model as a `.pkl` file.
- Saved the TF-IDF vectorizer as a `.pkl` file.
- Implemented priority classification using ticket text.
- Built a new-ticket prediction system.

## Conclusion

This project demonstrates how Natural Language Processing and Machine Learning can be used to automate IT support ticket classification.

The final system combines text preprocessing, TF-IDF feature extraction, machine learning classification, and rule-based priority assignment to provide an end-to-end IT support ticket classification workflow.

The Linear SVM model achieved approximately **85.69% accuracy** and was selected as the final category classification model.