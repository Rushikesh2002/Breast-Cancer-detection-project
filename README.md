A machine learning classification project for predicting whether a breast tumor is malignant or benign using the Breast Cancer Wisconsin (Diagnostic) dataset.

Disclaimer: This project is for educational and research purposes only. It is not a medical diagnostic system and should not be used to make clinical decisions.

Project Overview

This project demonstrates a complete beginner-friendly machine learning workflow:

Loading the Breast Cancer Wisconsin (Diagnostic) dataset

Exploring and manipulating the data

Creating a Pandas DataFrame

Visualizing the dataset

Splitting the data into training and testing sets

Applying feature scaling with StandardScaler

Training classification models

Evaluating predictions using accuracy, confusion matrix, and classification report

The notebook uses the dataset provided by scikit-learn through load_breast_cancer().

Dataset

The project uses the Breast Cancer Wisconsin (Diagnostic) dataset.

According to the dataset description:

569 instances

30 numeric predictive features

2 target classes

Malignant

Benign

212 malignant samples

357 benign samples

No missing attribute values are reported

The features are computed from digitized images of fine-needle aspirates (FNA) of breast masses and describe characteristics of cell nuclei.

Feature Groups

The 30 features include measurements such as:

Radius

Texture

Perimeter

Area

Smoothness

Compactness

Concavity

Concave points

Symmetry

Fractal dimension

These measurements are provided as:

Mean values

Standard error values

Worst/largest values

Machine Learning Workflow

Dataset
   |
   v
Data Loading
   |
   v
Data Exploration & Manipulation
   |
   v
Data Visualization
   |
   v
Train / Test Split
   |
   v
Feature Scaling
   |
   v
Model Training
   |
   v
Model Prediction
   |
   v
Model Evaluation

Models

Support Vector Classifier

The project trains an SVC model on the original features and evaluates its predictions.

It also trains an SVC model using standardized features.

The notebook reports an accuracy of approximately 96.49% for the scaled SVC model on its test set.

Logistic Regression

The project also uses LogisticRegression with L2 regularization.

The notebook reports an accuracy of approximately 96.49% for the Logistic Regression model on its test set.

The notebook also shows a convergence warning for the Logistic Regression run, indicating that scaling the data or increasing the iteration limit can be considered for improving model convergence.

Feature Scaling

StandardScaler is used to standardize the training and testing features:

from sklearn.preprocessing import StandardScaler

sc = StandardScaler()

X_train_sc = sc.fit_transform(X_train)
X_test_sc = sc.transform(X_test)

The scaler is fitted on the training data and then applied to the test data.

Evaluation Metrics

The project imports the following evaluation metrics from scikit-learn:

Accuracy Score

Confusion Matrix

Classification Report

These metrics can be used to understand how well the classification models perform on the test data.

Technologies Used

Python

NumPy

Pandas

Matplotlib

Seaborn

Scikit-learn

Jupyter Notebook / Google Colab

Installation

Clone the repository:

git clone <YOUR_GITHUB_REPOSITORY_URL>
cd breast-cancer-detection

Create a virtual environment:

python -m venv venv

Activate it on Windows:

venv\Scripts\activate

Activate it on macOS/Linux:

source venv/bin/activate

Install the required libraries:

pip install numpy pandas matplotlib seaborn scikit-learn jupyter

Running the Project

Start Jupyter Notebook:

jupyter notebook

Open the project notebook and run the cells sequentially.

If you are using Google Colab, upload the notebook and execute the cells there.

Project Structure

A suggested GitHub repository structure is:

breast-cancer-detection/
│
├── README.md
├── breast_cancer_detection.ipynb
├── breast_cancer_dataframe.csv
├── requirements.txt
└── images/
    └── model_results.png

The exact files may vary depending on how the project is organized.

Requirements

A requirements.txt file can contain:

numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter

Install them with:

pip install -r requirements.txt

Results

The notebook contains the following reported test-set accuracy results:

Model

Configuration

Accuracy

Support Vector Classifier

Original features

93.86%

Support Vector Classifier

Standardized features

96.49%

Logistic Regression

Original features

96.49%

These values are the results reported by the notebook for its particular train/test split and configuration. They should not be interpreted as clinical performance.

Dataset Reference

The dataset is the Breast Cancer Wisconsin (Diagnostic) dataset, originally associated with the UCI Machine Learning Repository and made available through scikit-learn.

The dataset description credits:

Dr. William H. Wolberg

W. Nick Street

Olvi L. Mangasarian

Future Improvements

Possible extensions for this project include:

Hyperparameter tuning

Cross-validation

ROC-AUC analysis

Precision, recall, and F1-score comparison

Improved confusion-matrix visualization

Feature importance / model interpretability

Pipeline-based preprocessing

Model serialization with joblib

Building a simple Streamlit interface

Adding automated tests

Adding experiment tracking

Disclaimer

This repository demonstrates machine learning classification using a public dataset. The predictions produced by this project are not medical diagnoses. Real-world medical applications require appropriate clinical validation, regulatory review, expert oversight, and evaluation on suitable clinical data.

Author

Your Name

If you found this project useful, feel free to ⭐ the repository
