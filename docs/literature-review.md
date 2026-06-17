# Literature Review: Zero-Day Network Anomaly Detection with Deep Learning

**Student:** _Kanwar Azlan_
**Updated:** _15 June 2026_

---

## Instructions

For each paper or resource you read, complete one entry below.
Aim for at least **10 papers** by the end of Week 2.
Use Google Scholar, IEEE Xplore, ACM DL, arXiv, or USENIX Security.

---

## Paper Summary Template

### Paper 1 — GTAE-IDS

| Field | Content |
|---|---|
| **Full title** | Graph Transformer-Based Autoencoder Framework for Real-Time Network Intrusion Detection |
| **Authors** | Jalal Ghadermazi , Soumyadeep Hore , Graduate Student Member, IEEE, Ankit Shah , Senior Member, IEEE, and Nathaniel D. Bastian , Senior Member, IEEE |
| **Year** | 2025 |
| **Venue** | Journal |
| **URL / DOI** | https://doi.org/10.1109/TIFS.2025.3557741 |
| **Method** | The GTAE-IDS framework operates as an unsupervised, packet-based network intrusion detection system designed for near real-time traffic analysis. The process is structured into two main components: Graph Generation and Anomaly Detection. Network traffic is continuously monitored via raw packet captures (.pcap), which are modeled as a dynamic graph based on time and packet events. Rather than utilizing the full network flow, the system extracts a specified sequence of the initial p packets. The framework leverages an asymmetrical Graph Transformer-Based Autoencoder (GTAE). The encoder utilizes graph transformer layers with a self-attention mechanism to learn and extract structural and contextual embeddings strictly from benign (normal) traffic data. |
| **Dataset** | CIC-IDS2017, CIC-IDS2018, ACI-IoT2023 |
| **Key result** | The framework demonstrates superior efficacy by achieving high-precision anomaly detection very early into a communication flow. On the CIC-IDS2017 dataset, the voting-based ensemble model achieved an optimal True Positive Rate (TPR) of 99.04% using a graph representation of just eight packets. When evaluating individual attack paths on CIC-IDS2017, the anomaly detection rate exceeded 98.5% across all specific network attack classes, showcasing significant performance leaps over flow-based GNNs on complex threats like WebAttack-BruteForce, Infiltration, and DoS Slowloris. Additionally, the model generalized remarkably well in new environments, maintaining detection results above 98% on the eight-packet graph representations for both the CIC-IDS2018 and ACI-IoT-2023 testing sets. In terms of operational efficiency, GTAE-IDS outperformed non-GNN state-of-the-art packet-level models by achieving the highest overall TPR (0.990) alongside a highly efficient inference time of just 1.28 microseconds per packet—which accounts for both graph generation and model inference. |
| **Limitation** | Despite its real-time processing benefits, the paper notes a constraint regarding the framework's initial setup overhead. The GTAE-IDS architecture requires a slightly longer offline training runtime compared to existing flow-based GNN approaches in the literature. Specifically, the model requires 5.43 hours of initial training time on the tested hardware infrastructure. This added computational footprint is driven by the complex computational requirements of incorporating a transformer-based design within the encoder segment. However, the authors argue that this increased initial training time is a one-time deployment investment that does not interfere with or degrade its swift real-time execution capabilities once operational. |
| **Relevance to our project** | This paper is highly relevant to our project as it also works on autoencoder based anomaly detection using network traffic dataset. These approaches can be very helpful in demonstrating the capability of the model and it's performance in detecting attacks specially zero-day. |

### Paper 2 — FL for Detection Using AE and GMM

| Field | Content |
|---|---|
| **Full title** | Federated learning for misbehaviour detection with variational autoencoders and Gaussian mixture models |
| **Authors** | Enrique Mármol Campos1, Aurora Gonzalez-Vidal1, José L. Hernández-Ramos1, Antonio Skarmeta1 |
| **Year** | 2025 |
| **Venue** | Journal |
| **URL / DOI** | https://doi.org/10.1007/s10207-025-01000-8 |
| **Method** | The paper presents an unsupervised, cloud-based Federated Learning (FL) framework designed to detect potential misbehavior in vehicular environments (such as vehicles transmitting false or malicious data). The framework avoids supervised training entirely and is executed over three distinct sequential phases: Local Density Estimation, Local Feature Extraction and Federated Fine-Tuning, Local Misbehavior Classification. |
| **Dataset** | VeReMi |
| **Key result** | The combined VAE and GMM model demonstrated notable performance jumps over traditional unsupervised baselines and supervised paradigms. In a detailed client division test focused on vehicles grouping around 298 optimal GMM components, the VAE model reached a localized encoder reconstruction accuracy of 97.2% at an optimized learning rate of $lr = 0.05$. When evaluating the absolute combined accuracy of the model (incorporating both the initial GMM screening and the VAE feature reconstruction layers), the system achieved a total structural accuracy of 82.4%, a precision of 67.2%, an F1-score of 77.5%, and an exceptional recall rate of 96.8%. Pairwise statistical checks using Kruskal-Wallis and Wilcoxon tests validated that the VAE significantly outperformed standard deterministic Autoencoders (AE). Furthermore, ablation analyses demonstrated that omitting the VAE tier dropped pure GMM tracking accuracy to 76%, whereas skipping the GMM altogether to rely solely on raw VAE error detection bottomed out accuracy at just 58.7%. |
| **Limitation** | The initial calibration phase mandates an entirely benign dataset to train both the GMM profiling and the VAE feature extractors properly. Securing a completely clean, attack-free dataset across an open vehicular network can be resource-intensive and structurally difficult to enforce. he mathematical optimization of the GMM relies heavily on the assumption that the operational dataset parameters align with normal Gaussian curves. If real-world road and networking conditions produce skewed or non-Gaussian feature bounds, the generalizability and performance of the model may degrade. Increasing the granularity and number of cluster components drastically escalates the processing duration. Running the iterative silhouette analysis phase to configure 300 optimal parameters required up to 110,132 seconds (nearly 30.5 hours), posing a steep processing overhead during model initialization. |
| **Relevance to our project** | This paper shows the autoencoder model used with GMM for the unsupervised learning dataset and acheived 97.2% accuracy rate with state-of-the-art models. This will effect can be used train and test our model. |

### Paper 3 — A Self-Adaptive Intrusion Detection System for Zero-Day Attacks Using Deep Q-Networks

| Field | Content |
|---|---|
| **Full title** | A Self-Adaptive Intrusion Detection System for Zero-Day Attacks Using Deep Q-Networks |
| **Authors** | Mouhammd Alkasassbeh; Ebtehal H. Omoush; Mohammad Almseidin; Amjad Aldweesh |
| **Year** | 2025 |
| **Venue** | Journal |
| **URL / DOI** | https://doi.org/10.1109/ACCESS.2025.3617792 |
| **Method** | This section presents the design and implementation of the proposed DQN-based intrusion detection system (IDS), which is evaluated using multiple experiments on the UGRansome dataset. The methodology comprises data preprocessing, environment modeling, agent design, training configuration, and evaluation strategies. First, incomplete records were removed to ensure data quality. Subsequently, features with high cardinality, such as SeedAddress, ExpAddress, and IPaddress, were eliminated to reduce the risk of overfitting. In addition, categorical attributes, including Protocol, Flag, Family, and Threats, were then transformed into a numerical format using the label encoding technique. |
| **Dataset** | UGRansome |
| **Key result** | the proposed self-learning IDS, leveraging Deep Q-Networks, has demonstrated its effectiveness in detecting both known and zero-day ransomware attacks with high accuracy and strong generalization capabilities across various classification scenarios. These findings underscore the potential of reinforcement learning as a robust and adaptive foundation for real-time intrusion detection in evolving threat landscapes |
| **Limitation** | the main limitations revolve around the computational expense of training and the interpretability of the model's decisions. However, the paper also outlines clear directions for future research to enhance the system's capabilities and address these challenges, particularly in terms of adaptability, explainability, and real-world deployment. |
| **Relevance to our project** | The paper proposed unsupervised learning framework to detect zero day attacks with Deep Q-Networks. This can be useful in understanding our own project model which is also based on Autoencoders-deep neural network. |

### Paper 4 — Name...

| Field | Content |
|---|---|
| **Full title** | An Intellectual Zero Trust Security Framework Using Deep Reinforcement Learning for Predictive Threat Mitigation in AI-Based Fraud Detection Systems |
| **Authors** | ANKUR MAHIDA |
| **Year** | 2026 |
| **Venue** | Journal |
| **URL / DOI** | https://doi.org/10.1109/ACCESS.2026.3664389 |
| **Method** | The proposed methodology involves the development of an Intelligent Zero Trust Security Framework where Machine Learning algorithm used to train the model is somewhat supervised while anomaly detection takes place, and the predictive mitigation engine is based on the Deep Reinforcement Learning algorithm. The whole system is used over an SDN enabled environment where the controller works as a intermediatory for heightening the flows, evaluating trust policies and enforcing security measures. The objective of the methodology is to change traditional reactive intrusion detection to proactive security model that is able to anticipate and mitigate attacks before they have severe impact. |
| **Dataset** | IEEE CIS Fraud Detection |
| **Key result** | Evaluation of the proposed DRL-Zero Trust model on a benchmark dataset of fraud detection shows that it significantly outperforms classical classifiers, including K Nearest Neighbor (KNN), Random Forest, Logistic Regression (LR) and Support Vector Machine (SVM). The proposed model achieved 98.7% accuracy, 98.4% precision, 98.9% recall and an Area Under the Receiver Operating Characteristic Curve (AUC-ROC) of 0.995, and is better resistant to zero-day attacks and adversarial instances. |
| **Limitation** |  Deep Reinforcement Learning agent training is computationally expensive and needs to be optimally tuned to reach convergence and stability. Since the quality and representativeness of the training data is critical to the efficiency of the model, even though DRL is more adaptive, highly sparse or biased training data can impact initial learning behaviour. The evaluation of the framework is done on simulated SDN environments and benchmark data, but a real-world deploymentcan bring other issues, such as encrypted traffic, compliance
requirements changes, and integration overhead with existing systems. The explainability of DRL decisions is still not as good as rule-based systems, and this can be a problem in regulatory and forensic analysis scenarios. |
| **Relevance to our project** | This framework analyze the deep re-inforcement model in fraud detection system for threat mitigation using zero-trust model. Similarly We can analyze this framrwork for building our zero-day attack detection and prediction model using the same unsupervised learning model startegy. The models used in the paper are SVM, KNN, LR and Autoencoder (stated in related work). We will introduce autoencoder in this same technique to compare the overall results. |

### Paper 5 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

### Paper 6 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

### Paper 7 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

### Paper 8 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

### Paper 9 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

### Paper 10 — Name...

| Field | Content |
|---|---|
| **Full title** |  |
| **Authors** |  |
| **Year** |  |
| **Venue** |  |
| **URL / DOI** |  |
| **Method** |  |
| **Dataset** |  |
| **Key result** |  |
| **Limitation** |  |
| **Relevance to our project** |  |

---

## Reference Table (Quick Overview)

| # | Title (short) | Authors | Year | Method | Dataset | Relevance |
|---|---|---|---|---|---|---|
| 1 | GTAE-IDS | Jalal Ghadermazi , Soumyadeep Hore , Graduate Student Member, IEEE, Ankit Shah , Senior Member, IEEE, and Nathaniel D. Bastian , Senior Member, IEEE | 2025 | The GTAE-IDS framework operates as an unsupervised, packet-based network intrusion detection system designed for near real-time traffic analysis. The process is structured into two main components: Graph Generation and Anomaly Detection. | CIC-IDS2017, CIC-IDS2018, ACI-IoT2023 | it also works on autoencoder based anomaly detection using network traffic dataset. |
| 2 | FL for Detection Using AE and GMM | Enrique Mármol Campos1, Aurora Gonzalez-Vidal1, José L. Hernández-Ramos1, Antonio Skarmeta1 | 2025 | The paper presents an unsupervised, cloud-based Federated Learning (FL) framework designed to detect potential misbehavior in vehicular environments (such as vehicles transmitting false or malicious data). The framework avoids supervised training entirely and is executed over three distinct sequential phases: Local Density Estimation, Local Feature Extraction and Federated Fine-Tuning, Local Misbehavior Classification. | VerMi | This paper shows the autoencoder model used with GMM for the unsupervised learning dataset and acheived 97.2% accuracy rate with state-of-the-art models. This will effect can be used train and test our model. |
| 3 | A Self-Adaptive IDS for Zero-Day Using DQN | Mouhammd Alkasassbeh; Ebtehal H. Omoush; Mohammad Almseidin; Amjad Aldweesh | 2025 | This section presents the design and implementation of the proposed DQN-based intrusion detection system (IDS), which is evaluated using multiple experiments on the UGRansome dataset. The methodology comprises data preprocessing, environment modeling, agent design, training configuration, and evaluation strategies. First, incomplete records were removed to ensure data quality. Subsequently, features with high cardinality, such as SeedAddress, ExpAddress, and IPaddress, were eliminated to reduce the risk of overfitting. In addition, categorical attributes, including Protocol, Flag, Family, and Threats, were then transformed into a numerical format using the label encoding technique. | UGRansome | The paper proposed unsupervised learning framework to detect zero day attacks with Deep Q-Networks. This can be useful in understanding our own project model which is also based on Autoencoders-deep neural network. |
| 4 | An Intellectual Zero Trust Security Framework Using DRL for Predictive Threat Mitigation in AI-Based Fraud Detection Systems | ANKUR MAHIDA | 2026 | The proposed methodology involves the development of an Intelligent Zero Trust Security Framework where Machine Learning algorithm used to train the model is somewhat supervised while anomaly detection takes place, and the predictive mitigation engine is based on the Deep Reinforcement Learning algorithm. The whole system is used over an SDN enabled environment where the controller works as a intermediatory for heightening the flows, evaluating trust policies and enforcing security measures. The objective of the methodology is to change traditional reactive intrusion detection to proactive security model that is able to anticipate and mitigate attacks before they have severe impact. | IEEE CIS Fraud Detection | This framework analyze the deep re-inforcement model in fraud detection system for threat mitigation using zero-trust model. Similarly We can analyze this framrwork for building our zero-day attack detection and prediction model using the same unsupervised learning model startegy. The models used in the paper are SVM, KNN, LR and Autoencoder (stated in related work). We will introduce autoencoder in this same technique to compare the overall results. |
| 5 | | | | | | |
| 6 | | | | | | |
| 7 | | | | | | |
| 8 | | | | | | |
| 9 | | | | | | |
| 10 | | | | | | |

---

## Tools and Datasets Identified

| Name | Type | URL | Notes |
|---|---|---|---|
| CIC-IDS2017 | Dataset | https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset | - |
| CIC-IDS2018 | Dataset | https://www.kaggle.com/datasets/primus11/cic-ids-2018-dataset | - |
| ACI-IoT2023 | Dataset | https://www.kaggle.com/datasets/emilynack/aci-iot-network-traffic-dataset-2023 | - |
| Wireshark | Library / Tool | https://www.wireshark.org/download.html | - |
| Grid Search | Library / Tool | https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html | - |
| VeRMi | Dataset | [https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset](https://www.kaggle.com/datasets/haider094/veremi-dataset) | - |
| Viens | Library / Tool | [https://www.wireshark.org/download.html](https://veins.car2x.org/) | - |
| UGRansome | Dataset | https://www.kaggle.com/datasets/nkongolo/ugransome-dataset | - |
| Python | Library / Tool | https://www.python.org | - |
| Pytorch | Library / Tool | https://www.pytorch.org | - |
| Pandas | Library / Tool | https://www.Pandas.org | - |
| Numpy | Library / Tool | https://www.Numpy.org | - |
| Scikit Learn | Library / Tool | https://www.Scikitlearn.org | - |
| Matplotlib | Library / Tool | https://www.Matplotlib.org | - |
| IEEE-CIS | Dataset | https://www.kaggle.com/competitions/ieee-fraud-detection | - |



**Notes / Quotes:**
_This literature review file has been updated in the following manner:_

_1. The details of the research paper has been attached under "Paper Summary Template"._

_2. The "Quick Reference" Table has been updated with all the contents of the research papers for a quick overview._

_3. All the datasets, tools and libraries were combined under the "Tools and Datasets Identified" table._

