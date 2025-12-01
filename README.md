# 🚨 AI-Powered Network Threat Detection

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Status](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Framework](https://img.shields.io/badge/Framework-Scikit--Learn%20%7C%20XGBoost-orange)

> A scalable, adaptive, and accurate AI-powered system designed to detect suspicious activities and anomalies in real-time network traffic.

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Dataset](#-dataset)
- [Project Pipeline](#-project-pipeline)
- [Model Performance](#-model-performance)
- [Technologies Used](#-technologies-used)
- [Installation & Usage](#-installation--usage)
- [Future Work](#-future-work)

---

## 📖 Overview
With the rapid increase in cyberattacks, traditional rule-based intrusion detection systems often struggle to adapt to new and evolving threats. This project leverages **Machine Learning** to build an intelligent intrusion detection system (IDS) capable of differentiating between benign and malicious network traffic patterns.

The system analyzes network flow features to detect attacks such as:
* **DDoS Attacks**
* **Port Scanning**
* **Brute Force Attempts**
* **Botnet Activities**

## ❓ Problem Statement
**How can we design a scalable, adaptive, and accurate AI-powered system to detect suspicious activities in network traffic?**

Traditional systems rely on static signatures. This project utilizes dynamic feature analysis including packet flow rates, inter-arrival times, and TCP flags to identify anomalies that deviate from normal behavior.

---

## 📊 Dataset
The model is trained on the **Network Intrusion Dataset (CIC-IDS2017/2018)**, which contains comprehensive network traffic data including benign and common attacks.

* **Source:** [Kaggle - Network Intrusion Dataset](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)
* **Features:** 70+ flow features (e.g., `Flow Duration`, `Total Fwd Packets`, `Destination Port`, `Packet Length`).
* **Target:** Multi-class classification (Benign vs. various Attack types).

---

## 🛠 Project Pipeline

### 1. Data Preprocessing
* **Cleaning:** Removal of duplicates and handling of null/infinite values.
* **Optimization:** Downcasting numerical columns (`int64` $\to$ `int32`, `float64` $\to$ `float32`) to optimize memory usage.
* **Filtering:** Dropping columns with zero variance (single unique value) such as `Bwd PSH Flags` and `Fwd Avg Bytes/Bulk`.

### 2. Exploratory Data Analysis (EDA)
* **Distribution Analysis:** Visualizing the imbalance between Benign traffic and Attack classes using Count plots and Pie charts.
* **Correlation Analysis:** Identifying highly correlated features to reduce multicollinearity.

### 3. Feature Engineering & Selection
* **ANOVA F-Test:** Using `SelectKBest` to identify the most discriminative features.
* **PCA:** Principal Component Analysis for dimensionality reduction.
* **Redundancy Removal:** Dropping duplicate columns like `Fwd Header Length.1`.

### 4. Model Training
The following machine learning algorithms were implemented and tuned:
* **Random Forest Classifier:** Tuned using `RandomizedSearchCV` for optimal hyperparameters (Depth, Estimators, Split criteria).
* **XGBoost Classifier:** Implemented with categorical support and log-loss evaluation for high-performance gradient boosting.

---

## 📈 Model Performance

The table below summarizes the performance of the machine learning models deployed in this project:

| Model Name | Accuracy | Precision | Recall | F1-Score | Training Time |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest** | 99.8% | 0.99 | 0.99 | 0.99 | Fast |
| **XGBoost** | 99.9% | 0.99 | 0.99 | 0.99 | Moderate |
| **Decision Tree** | 98.5% | 0.98 | 0.98 | 0.98 | Very Fast |

> *Note: Results indicate the models are highly effective at distinguishing between normal traffic and intrusions.*

---

## 💻 Technologies Used
* **Language:** Python 3.x
* **Libraries:**
    * `Pandas` & `Numpy`: Data manipulation and memory optimization.
    * `Matplotlib` & `Seaborn`: Data visualization.
    * `Scikit-learn`: Model building, PCA, and Hyperparameter tuning.
    * `XGBoost`: Advanced gradient boosting implementation.

---

## 🚀 Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/ziadalaa7/AI-Network-Threat-Detection.git](https://github.com/ziadalaa7/AI-Network-Threat-Detection.git)
    cd AI-Network-Threat-Detection
    ```

2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost
    ```

3.  **Download the Dataset:**
    Download the dataset from [Kaggle](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset) and extract it into the project directory.

4.  **Run the Notebook:**
    Open `AI_Powered_Network_Threat_Detection.ipynb` in Jupyter Notebook or Google Colab to reproduce the training and evaluation steps.

---

## 🔮 Future Work
* **Deep Learning Integration:** Experimenting with LSTM or Autoencoders for sequential traffic analysis.
* **Real-time Deployment:** Wrapping the model in a Flask/FastAPI app to process live packet captures.
* **Explainability:** Using SHAP or LIME to visualize why a specific packet flow was flagged as a threat.

---

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/ziadalaa7/AI-Network-Threat-Detection/issues).

---

## 📝 License
This project is licensed under the [MIT License](LICENSE).
