Credit Card Fraud Detection using Machine Learning

Overview

This project focuses on detecting fraudulent credit card transactions using machine learning techniques. Credit card fraud is a significant issue in financial systems, and identifying fraudulent transactions quickly and accurately is essential.

The dataset used in this project is highly imbalanced, where fraudulent transactions represent a very small percentage of the total data. To handle this challenge, machine learning models such as Random Forest and XGBoost were implemented and tuned to improve fraud detection performance.

The final model achieves strong performance while balancing precision and recall, which is critical for real-world fraud detection systems.

---

Dataset

The dataset used in this project contains anonymized credit card transactions.

- Source: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud
- Total Transactions: 284,807
- Fraudulent Transactions: 492
- Features: 30 numerical features (V1–V28, Time, Amount)
- Target Variable: "Class"
  - "0" → Normal Transaction
  - "1" → Fraudulent Transaction

Due to GitHub file size limits, the dataset is not included in this repository.

How to Use the Dataset

1. Download the dataset from Kaggle.
2. Place "creditcard.csv" in the project directory before running the notebook.

---

Project Structure

credit-card-fraud-detection
│
├── images
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── feature_importance.png
│
├── notebook
│   └── fraud_detection.ipynb
│
├── .gitignore
├── requirements.txt
└── README.md

---

Machine Learning Workflow

1. Data Preprocessing

- Loaded and inspected the dataset
- Removed rows containing missing values
- Checked class imbalance
- Separated features and target variable

2. Train-Test Split

The dataset was split into training and testing sets while preserving the fraud ratio.

3. Models Used

Several models were tested:

- Logistic Regression (baseline)
- Random Forest Classifier
- XGBoost Classifier

4. Handling Class Imbalance

Fraud transactions are extremely rare, so class weighting was applied to help the model learn minority class patterns.

5. Hyperparameter Tuning

XGBoost parameters were tuned to improve model performance:

- "n_estimators = 700"
- "max_depth = 5"
- "learning_rate = 0.01"
- "scale_pos_weight = 15"

---

Model Performance

Final model evaluation metrics:

Metric| Score
Recall| 0.84
Precision| 0.84
F1 Score| 0.84
ROC-AUC| 0.98

These results show that the model can detect the majority of fraud cases while maintaining low false alarms.

---

Confusion Matrix

"Confusion Matrix" (images/confusion_matrix.png)

Confusion matrix interpretation:

- True Negatives: 71,071 normal transactions correctly classified
- False Positives: 18 normal transactions incorrectly flagged as fraud
- False Negatives: 18 fraud transactions missed
- True Positives: 95 fraud transactions correctly detected

---

ROC Curve

"ROC Curve" (images/roc_curve.png)

The ROC curve shows the model’s ability to distinguish between fraudulent and normal transactions.

ROC-AUC Score: 0.98
This indicates excellent classification performance.

---

Feature Importance

"Feature Importance" (images/feature_importance.png)

The XGBoost model highlights the most important features contributing to fraud detection.

Top influential features include:

- V14
- V4
- V12
- V10
- V7

These features represent key patterns that help distinguish fraudulent behavior from legitimate transactions.

---

Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Jupyter Notebook

---

How to Run the Project

1. Clone the repository

git clone https://github.com/[yourusername]/credit-card-fraud-detection.git

2. Navigate to the project folder

cd credit-card-fraud-detection

3. Install required packages

pip install -r requirements.txt

4. Open the notebook

jupyter notebook

5. Run the notebook file

notebook/fraud_detection.ipynb

---

Key Learnings

Through this project, the following concepts were explored:

- Handling highly imbalanced datasets
- Model evaluation using precision, recall, F1 score, and ROC-AUC
- Hyperparameter tuning for gradient boosting models
- Visualizing model performance with confusion matrices and ROC curves
- Interpreting model behavior through feature importance

---

Future Improvements

Possible improvements for this project include:

- Implementing SMOTE or advanced resampling techniques
- Trying additional models such as LightGBM
- Building a real-time fraud detection API
- Deploying the model using Flask or FastAPI

---

Author

Dipen Parmar

Machine Learning Enthusiast exploring data-driven solutions to real-world problems.
