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

---

## Reference Table (Quick Overview)

| # | Title (short) | Authors | Year | Method | Dataset | Relevance |
|---|---|---|---|---|---|---|
| 1 | GTAE-IDS | Jalal Ghadermazi , Soumyadeep Hore , Graduate Student Member, IEEE, Ankit Shah , Senior Member, IEEE,
and Nathaniel D. Bastian , Senior Member, IEEE | 2025 | The GTAE-IDS framework operates as an unsupervised, packet-based network intrusion detection system designed for near real-time traffic analysis. The process is structured into two main components: Graph Generation and Anomaly Detection. | CIC-IDS2017, CIC-IDS2018, ACI-IoT2023 | it also works on autoencoder based anomaly detection using network traffic dataset. |
| 2 | FL for Detection Using AE and GMM | Enrique Mármol Campos1, Aurora Gonzalez-Vidal1, José L. Hernández-Ramos1, Antonio Skarmeta1 | 2025 | The paper presents an unsupervised, cloud-based Federated Learning (FL) framework designed to detect potential misbehavior in vehicular environments (such as vehicles transmitting false or malicious data). The framework avoids supervised training entirely and is executed over three distinct sequential phases: Local Density Estimation, Local Feature Extraction and Federated Fine-Tuning, Local Misbehavior Classification. | VerMi | This paper shows the autoencoder model used with GMM for the unsupervised learning dataset and acheived 97.2% accuracy rate with state-of-the-art models. This will effect can be used train and test our model. |
| 3 | | | | | | |
| 4 | | | | | | |
| 5 | | | | | | |

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


**Notes / Quotes:**
_This literature review file has been updated in the following manner:_

_1. The details of the research paper has been attached under "Paper Summary Template"._

_2. The "Quick Reference" Table has been updated with all the contents of the research papers for a quick overview._

_3. All the datasets, tools and libraries were combined under the "Tools and Datasets Identified" table._

