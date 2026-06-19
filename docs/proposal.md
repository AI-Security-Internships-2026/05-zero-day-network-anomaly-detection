<img width="1833" height="70" alt="image" src="https://github.com/user-attachments/assets/4a379f54-6d1f-4e44-9e01-ba56e39bc0e4" /># Research Proposal: Zero-Day Network Anomaly Detection with Deep Learning

**Student:** _Kanwar Azlan_
**Supervisor:** _[Fill in supervisor name]_
**Start date:** _8th June 2026_
**Expected end date:** _[Fill in]_

---

## 1. Background

Build an unsupervised deep-learning model (autoencoder / transformer) that detects zero-day network intrusions on live packet captures without prior knowledge of the attack signature.

This project is carried out within the AI Security research agenda of CNIT/PNTLab Pisa (TECIP, Scuola Superiore Sant'Anna).

---

## 2. Problem Statement

_Existing studies on zero-day attack detection persist several key limitations including unsupervised approach, limited dataset and state-of-the-art models. Recent Study have shown that researchers still uses supervised / Semi-supervised or Deep learning moedels neglecting the importance of unseen attack data like we use in an unsupervised learning framework to detect and predict zero-days in network traffic._

---

## 3. Research Questions

1. _How the interaction graph analysis provide detailed accuracy and efficiency in network traffic analysis?_
2. _What measure can be made to enhance the accuracy for the real-time network traffic detection for unknown attacks?_
3. _Can other unsupervised ML models improve the overall detection performance of the network traffic?_
4. _Unlike a single Graph analysis framework, can ensemble learning approach be more effective in detecting unknown attack results?_

---

## 4. Proposed Methodology

### 4.1 Data Collection / Dataset

_For this project we are starting with CIC-IDS2017 Benchmark Dataset. You can access the dataset using the link below:_

_https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset_

### 4.2 Approach

_The framework of zero-day detection consist of multiple phases, each with its own functionality. The process starts with preprocessing of the dataset CIC-IDS 2017 which contains both benign and attack traffic. The irrelevant values like NAN, NULL and large values were removed in the preprocessing. The model undergoes training phases with only benign data. The model were trained on benign only data and tested with attack data, in this way we keep our framework in an unsupervised manner. Once the model is trained, it will be tested on attack data but without labels. The labels were removed from the dataset before testing. The output of the model will be evaluated with the attack labels using confusion metrics._

### 4.3 Evaluation Metrics

_The evaluation will be done using Confusion Metrics:_

1. _Precision_
2. _Recall_
3. _F1-Measure_
4. _Accuracy_
5. _ROC-AUC Curve_
6. __

### 4.4 Tooling

1. _Python_
2. _Pandas_
3. _Numpy_
4. _Metplotlib_
5. _Google Colab_
6. _Autoencoder (ML Model)_

---

## 5. Expected Outcome

_Describe the expected deliverable: a prototype, a benchmark, a dataset, a paper draft, etc._

---

## 6. Risks and Mitigations

| Risk | Likelihood | Mitigation |
|---|---|---|
| Dataset not publicly available | Medium | Use synthetic data or reach out to CNIT partners |
| Compute resources insufficient | Low | Use university HPC cluster |
| Scope too broad | High | Focus on one sub-problem; extend if time allows |

---

_Last updated: 2026-_
