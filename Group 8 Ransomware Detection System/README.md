# 🛡️ Ransomware Behavior Detection System (RBDS)
### 🎓 Group 8 – RSET 2022–26 S8 Project

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![ML](https://img.shields.io/badge/ML-LightGBM%20%7C%20LSTM-green)
![Frontend](https://img.shields.io/badge/Frontend-HTML%20%7C%20Bootstrap-blue)
![Firebase](https://img.shields.io/badge/Database-Firebase-orange)
![Status](https://img.shields.io/badge/Status-Active-success)

---

## 📌 Overview
The **Ransomware Behavior Detection System (RBDS)** is a hybrid machine learning-based system that detects ransomware using **disk + memory behavioral patterns**.

The system uses:
- **LightGBM** → fast static detection  
- **LSTM** → deep sequential behavioral analysis  

It monitors system activity, processes logs, classifies threats, and displays results in a **real-time web dashboard**.

---

## 🚀 Key Features
- 🔍 Real-time ransomware detection  
- 🧠 Hybrid ML model (LightGBM + LSTM)  
- 📊 Sliding window behavioral analysis  
- 📈 Web dashboard with live analytics  
- 🔥 Firebase integration for logging  
- 🧾 Detailed system logs visualization  
- ⚡ Fast + Deep detection pipeline  

---


---

## 🧠 Machine Learning Pipeline

### 🔹 LightGBM Pipeline
- Uses **ATA disk write logs**
- Sliding window:
  - Window size: 20 seconds  
  - Stride: 2 seconds  
- Extracted features:
  - Size statistics  
  - Entropy patterns  
  - LBA uniqueness  
  - Entropy spikes  

📄 See preprocessing script: :contentReference[oaicite:0]{index=0}  

---

### 🔹 LSTM Pipeline
- Combines:
  - Disk events  
  - Memory events  
- Window size: **100 ms**
- Sequence length: **50 windows**

Extracted features:
- Memory write behavior  
- Disk write behavior  
- Entropy trends  
- Temporal patterns  

📄 See preprocessing script: :contentReference[oaicite:1]{index=1}  

---

### 🔹 Classification Strategy
- LightGBM outputs probability:
  - `< threshold` → BENIGN  
  - `> threshold` → RANSOMWARE  
  - else → UNCERTAIN  

- LSTM performs:
  - Sequential pattern detection  
  - Binary classification (Benign / Ransomware)  

📄 Full pipeline: :contentReference[oaicite:2]{index=2}  

---

## 🌐 Frontend Dashboard

The system includes a **web-based monitoring dashboard** built using HTML, Bootstrap, and Firebase.

### 🔹 Pages

#### 🏠 Dashboard
- Shows system status (SAFE / THREAT)
- Displays:
  - Processes monitored  
  - Threats blocked  
  - Latest detection window  

📄 File: :contentReference[oaicite:3]{index=3}  

---

#### 📜 Logs Page
- Displays all detection logs
- Includes:
  - LightGBM result  
  - LSTM result  
  - Action taken (kill/allow)  

📄 File: :contentReference[oaicite:4]{index=4}  

---

#### 📊 Analytics Page
- Displays detection distribution
- Uses Chart.js donut chart
- Shows ransomware percentage  

📄 File: :contentReference[oaicite:5]{index=5}  

---

#### 🔐 Login Page
- Simple authentication UI  

📄 File: :contentReference[oaicite:6]{index=6}  

---

## 🛠️ Tech Stack

### 🔹 Backend / ML
- Python  
- Pandas  
- NumPy  
- LightGBM  
- TensorFlow / Keras (LSTM)  

### 🔹 Frontend
- HTML  
- Bootstrap  
- Chart.js  

### 🔹 Database
- Firebase Firestore  

### 🔹 Tools
- Google Colab  
- Google Cloud Storage (GCS)  
- Sysmon logs  

---


---

## ⚙️ Installation & Setup

### ✅ Prerequisites
- Python 3.8+
- Node.js (optional)
- Firebase account

---


