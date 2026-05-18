# Student_Risk_Detection_System

AI-powered student risk detection and academic anomaly analysis system using Isolation Forest, K-Means clustering, and Autoencoder-based reconstruction error to proactively identify at-risk students through behavioral and performance analytics.

---

# Overview

This repository presents an AI-driven **Student Risk Detection System** designed to help educational institutions that are providing online education proactively identify students who may be academically at risk.

The system combines:

- Unsupervised anomaly detection
- Clustering-based cohort profiling
- Deep learning reconstruction analysis
- Risk aggregation logic
- Interactive Streamlit deployment

The goal is to detect abnormal academic, engagement, and behavioral patterns before severe academic decline occurs.

This project was developed during the **HackAVENSIS Hackathon** and later completed into a full SaaS-style prototype after the competition.

---

# Problem Statement

Educational institutions that provide online education often struggle to identify academically vulnerable students early enough for intervention.

Traditional monitoring methods are:
1. Reactive instead of proactive
2. Dependent on manual observation
3. Unable to scale across large student populations
4. Limited in detecting hidden behavioral risk patterns

There is a need for a scalable AI-driven system capable of continuously analyzing academic and engagement data to identify students requiring support.

---

# Solution Summary

The proposed system:

1. Processes academic and behavioral datasets
2. Detects anomalous student behavior using machine learning
3. Profiles student groups using clustering
4. Uses deep learning reconstruction error for hidden risk detection
5. Aggregates multiple AI signals into a final risk score
6. Displays results through an interactive frontend dashboard

---

# System Architecture

The solution follows a multi-stage unsupervised risk detection pipeline.

---

# Student Risk Detection Pipeline

## Stage 1: Isolation Forest (Anomaly Detection)

1. Scaled features are passed through an Isolation Forest model
2. The model isolates abnormal academic behavior patterns
3. Students with unusual engagement or performance characteristics receive anomaly flags

### Why Isolation Forest?

Isolation Forest works effectively for:
- Unsupervised anomaly detection
- High-dimensional academic datasets
- Rare behavioral deviations
- Early risk identification without labeled data

### Output
- Anomaly score
- Binary anomaly flag

---

## Stage 2: K-Means Clustering (Cohort Risk Profiling)

1. Students are grouped into behavioral cohorts using K-Means clustering
2. Each cluster represents a specific engagement/performance profile
3. Cluster-level risk scores are calculated using anomaly density

### Why Clustering?

Clustering helps:
- Contextualize anomalies
- Compare students within similar groups
- Reduce false positives
- Identify high-risk academic cohorts

### Output
- Cluster ID
- Cluster risk score

---

## Stage 3: Autoencoder-Based Reconstruction Analysis

1. A deep learning Autoencoder learns normal student behavior patterns
2. The model attempts to reconstruct input feature vectors
3. High reconstruction error indicates abnormal hidden patterns

### Why Autoencoder?

The Autoencoder:
- Learns latent academic behavior structures
- Detects subtle non-linear deviations
- Works without labeled at-risk examples

### Output
- Reconstruction error
- Autoencoder risk flag

---

## Stage 4: Final Risk Aggregation

The final student risk score combines:

1. Cluster risk score
2. Isolation Forest anomaly flag
3. Autoencoder reconstruction flag

### Risk Formula

```python
final_risk_score = (
    0.4 * cluster_risk +
    0.3 * iso_flag +
    0.3 * ae_flag
)

```

Students exceeding the threshold are classified as:

- At-Risk
- Requires Monitoring
- Normal

---

# Model Details

## Isolation Forest
- Framework: Scikit-learn
- Purpose: Statistical anomaly detection for online student behavioral data

## K-Means Clustering
- Framework: Scikit-learn
- Purpose: Cohort-based student engagement and academic profiling

## Autoencoder
- Framework: TensorFlow / Keras
- Loss Function: Mean Squared Error (MSE)
- Optimizer: Adam

The Autoencoder reconstructs student feature vectors and uses reconstruction error as an anomaly signal to identify hidden academic risk patterns.

---

# Technology Stack

## Machine Learning
1. Python
2. Scikit-learn
3. TensorFlow / Keras

## Data Processing
1. Pandas
2. NumPy

## Frontend
1. Streamlit
2. HTML
3. CSS

---

# Prototype Frontend

A complete Streamlit-based frontend has been integrated to demonstrate the full student risk detection pipeline for online educational institutions.

The prototype supports:

- Uploading trained ML models
- Uploading student CSV datasets
- Running the complete AI pipeline
- Viewing risk dashboards
- Viewing flagged at-risk students
- Interactive frontend-based academic risk screening

Additionally, a custom HTML/CSS login interface was integrated for controlled access and presentation flow during hackathon demonstrations.

---

# Frontend Workflow

The deployed frontend consists of:

1. HTML/CSS Login Page
2. Streamlit Backend Interface
3. AI-Based Student Risk Detection Pipeline

The login page redirects users to the deployed Streamlit application through an ngrok-generated public URL.

---

# Steps to Run the Frontend (Colab)

## Step 1: Open the Notebook

1. Open the folder **`Website_Code`**
2. Open:

```text
student_risk_detection_app.ipynb
```

3. Click **Open in Colab**

---

## Step 2: Upload Frontend Assets

Before running the notebook:

1. Open the **`assets`** folder
2. Upload all frontend asset files into the Colab session

These assets are required for:
- Login page rendering
- CSS styling
- Frontend integration

---

## Step 3: Configure ngrok

1. Create a free ngrok account:

```text
https://dashboard.ngrok.com/get-started/your-authtoken
```

2. Replace the placeholder token inside the notebook:

```python
ngrok.set_auth_token("YOUR_NGROK_AUTH_TOKEN")
```

---

## Step 4: Run the Notebook

1. Click:

```text
Runtime → Run all
```

2. Wait for execution to complete

3. A public ngrok URL will be generated similar to:

```text
https://example-name.ngrok-free.dev
```

---

## Step 5: Connect Login Page to Streamlit

After the ngrok URL is generated:

1. Open the login page file:

```text
login.html
```

2. Locate the following line:

```javascript
window.location.href = "YOUR_NGROK_LINK";
```

3. Replace the placeholder URL with your generated ngrok URL

Example:

```javascript
window.location.href = "https://example-name.ngrok-free.dev";
```

---

## Step 6: Launch the System

1. Open the modified:

```text
login.html
```

2. The login page will redirect to the Streamlit application

3. Upload:
- `model.pkl`
- `autoencoder.keras`
- Student CSV dataset

4. Run the complete student risk detection pipeline

---

# Key Features

- Unsupervised student risk detection
- AI-driven academic analytics
- Autoencoder reconstruction analysis
- Clustering-based student profiling
- Interactive Streamlit deployment
- Login page integration
- CSV-based predictions
- SaaS-style frontend prototype
- Early intervention support for online educational institutions

---

# Future Improvements

1. Real-time database integration
2. FastAPI backend deployment
3. Live institutional dashboards
4. Student intervention recommendation engine
5. Explainable AI visualizations
6. Multi-role authentication system
7. Cloud deployment support
8. Real-time student activity monitoring

---

# Pictures

## PC View

(Add screenshots here)

---

## Mobile View

(Add screenshots here)

---
