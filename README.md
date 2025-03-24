ML Agent for Predicting and Remediating Kubernetes Cluster Issues
Overview
This project aims to predict and remediate failures in Kubernetes clusters by analyzing logs and system metrics. It uses Machine Learning (ML) models to detect:
✔ Pod Failures
✔ Resource Exhaustion (CPU, Memory, Disk)
✔ Network Issues

The models are built using anomaly detection, time-series forecasting, and classification algorithms to identify potential failures before they escalate.

Project Structure
1. src/ - Data Preprocessing
This folder contains the Jupyter Notebook (.ipynb) file for data preprocessing.
Loads the dataset and cleans missing or inconsistent values.
Normalizes feature values for improved ML model performance.
Converts categorical variables where necessary.
Splits data into training and testing sets.

2. models/ - ML Models for Failure Prediction
This folder includes the trained models for different failure types:

🟢 Pod Failures
📌 Techniques Used:

Anomaly Detection: Isolation Forest (Unsupervised Learning)
Time-Series Forecasting: LSTM (Supervised Learning)
📌 Steps:
Loads dataset and normalizes CPU, memory, and network usage.
Converts pod status to binary (failure or normal).
Uses Isolation Forest to detect abnormal resource usage patterns.
Implements LSTM to predict future failures based on past 10 timestamps.
Combines both models to make a final failure prediction.

🟡 Resource Exhaustion (CPU, Memory, Disk)
📌 Techniques Used:

LSTM (Time-Series Analysis)
XGBoost Classifier
📌 Steps:
Preprocesses dataset and normalizes system metrics.
Defines threshold-based binary labels (resource exhaustion if usage > 90%).
Trains LSTM for detecting patterns in time-series data.
Trains XGBoost Classifier as an alternative model.
Evaluates models with accuracy scores and classification reports.
🔴 Network Issues
📌 Techniques Used:

LSTM (Sequential Data Analysis)

XGBoost Classifier
📌 Steps:
Loads network-related metrics (e.g., packets received/transmitted, dropped).
Converts timestamps to datetime format.
Computes total dropped packets as a key indicator of network failures.
Normalizes feature values using MinMaxScaler.
Trains LSTM to detect network failures over time.
Trains XGBoost Classifier to classify network issues.

3. data/ - Dataset
Contains the datasets used in this project:
Raw Dataset: The original dataset containing system logs and metrics.
Preprocessed Dataset: The cleaned and formatted dataset after preprocessing.

4. presentation/ - Presentation Files
Contains slides and documents for presenting the project.

5. README.md (This File)
Provides a structured overview of the project, including its purpose, methodology, and folder descriptions.

Installation & Setup
1️⃣ Clone this repository:

bash
Copy
Edit
git clone https://github.com/yourusername/ML-Agent-for-Predicting-and-Remediating-Kubernetes-Cluster-Issues.git
cd ML-Agent-for-Predicting-and-Remediating-Kubernetes-Cluster-Issues
2️⃣ Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
3️⃣ Run the preprocessing notebook in src/.
4️⃣ Train and test models in the models/ folder.

