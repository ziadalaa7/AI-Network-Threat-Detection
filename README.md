# 🚨 AI-Powered Network Threat Detection

Cyberattacks grow more sophisticated every day, and traditional security tools often struggle to keep up.  
This project introduces an **AI-powered system** that analyzes network traffic and automatically identifies suspicious activities such as:

- Hacking attempts  
- Data theft  
- Denial-of-service (DoS) attacks  

The system **continuously learns** from new threats, making it more adaptive and reliable than traditional methods.

---

## 🎯 Key Goals
- Monitor network traffic in real time  
- Detect threats early and send alerts  
- Reduce the burden on IT security teams  
- Scale to handle large networks and enterprise environments  

---

## 📊 Dataset

This project uses the **CIC-IDS-2017 dataset**, one of the most comprehensive intrusion detection datasets available.

Dataset source:  
[CIC-IDS-2017 on Kaggle](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)

The dataset includes:

- Normal and attack traffic  
- Multiple attack categories (e.g., DDoS, brute force, infiltration)  
- Flow-based features (packet counts, duration, protocol, etc.)  
- Realistic simulated enterprise traffic patterns  

---

## 📘 Notebook

The full model pipeline, preprocessing, EDA, and training steps are implemented in the Jupyter Notebook below:

Notebook link:  
https://github.com/ziadalaa7/AI-Network-Threat-Detection/blob/19419496b980bc1023c57935072d058f9c5e6741/AI-Powered%20Network%20Threat%20Detection%20.ipynb

This notebook includes:

- Data loading  
- Exploratory data analysis  
- Threat detection model training  
- Evaluation metrics and visualizations  

---

## 🧠 Features

- Data ingestion and validation  
- Exploratory Data Analysis (EDA)  
- Data preprocessing (encoding, scaling, cleaning)  
- Machine learning model training and evaluation  
- Detection of malicious vs. normal network traffic  
- Modular and scalable pipeline design  

---

## 🔧 Project Workflow

### 1. Data Loading
Loads network traffic logs containing fields such as:
- Source and destination IP  
- Protocol  
- Packet/byte counts  
- Attack label  

Example:
```python
data = pd.read_csv("your_dataset.csv")
