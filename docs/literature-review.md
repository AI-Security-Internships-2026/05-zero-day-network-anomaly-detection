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
| **Authors** | Jalal Ghadermazi , Soumyadeep Hore , Graduate Student Member, IEEE, Ankit Shah , Senior Member, IEEE,
and Nathaniel D. Bastian , Senior Member, IEEE |
| **Year** | 2025 |
| **Venue** | Journal |
| **URL / DOI** | https://doi.org/10.1109/TIFS.2025.3557741 |
| **Method** | The GTAE-IDS framework operates as an unsupervised, packet-based network intrusion detection system designed for near real-time traffic analysis. The process is structured into two main components: Graph Generation and Anomaly Detection. Network traffic is continuously monitored via raw packet captures (.pcap), which are modeled as a dynamic graph based on time and packet events. Rather than utilizing the full network flow, the system extracts a specified sequence of the initial p packets. The framework leverages an asymmetrical Graph Transformer-Based Autoencoder (GTAE). The encoder utilizes graph transformer layers with a self-attention mechanism to learn and extract structural and contextual embeddings strictly from benign (normal) traffic data. |
| **Dataset** | CIC-IDS2017, CIC-IDS2018, ACI-IoT2023 |
| **Key result** | The framework demonstrates superior efficacy by achieving high-precision anomaly detection very early into a communication flow. On the CIC-IDS2017 dataset, the voting-based ensemble model achieved an optimal True Positive Rate (TPR) of 99.04% using a graph representation of just eight packets. When evaluating individual attack paths on CIC-IDS2017, the anomaly detection rate exceeded 98.5% across all specific network attack classes, showcasing significant performance leaps over flow-based GNNs on complex threats like WebAttack-BruteForce, Infiltration, and DoS Slowloris. Additionally, the model generalized remarkably well in new environments, maintaining detection results above 98% on the eight-packet graph representations for both the CIC-IDS2018 and ACI-IoT-2023 testing sets. In terms of operational efficiency, GTAE-IDS outperformed non-GNN state-of-the-art packet-level models by achieving the highest overall TPR (0.990) alongside a highly efficient inference time of just 1.28 microseconds per packet—which accounts for both graph generation and model inference. |
| **Limitation** | Despite its real-time processing benefits, the paper notes a constraint regarding the framework's initial setup overhead. The GTAE-IDS architecture requires a slightly longer offline training runtime compared to existing flow-based GNN approaches in the literature. Specifically, the model requires 5.43 hours of initial training time on the tested hardware infrastructure. This added computational footprint is driven by the complex computational requirements of incorporating a transformer-based design within the encoder segment. However, the authors argue that this increased initial training time is a one-time deployment investment that does not interfere with or degrade its swift real-time execution capabilities once operational. |
| **Relevance to our project** | This paper is highly relevant to our project as it also works on autoencoder based anomaly detection using network traffic dataset. These approaches can be very helpful in demonstrating the capability of the model and it's performance in detecting attacks specially zero-day. |

**Notes / Quotes:**
> _Paste important quotes or your personal notes here._

---

## Reference Table (Quick Overview)

| # | Title (short) | Authors | Year | Method | Dataset | Relevance |
|---|---|---|---|---|---|---|
| 1 | GTAE-IDS | Jalal Ghadermazi , Soumyadeep Hore , Graduate Student Member, IEEE, Ankit Shah , Senior Member, IEEE,
and Nathaniel D. Bastian , Senior Member, IEEE | 2025 | The GTAE-IDS framework operates as an unsupervised, packet-based network intrusion detection system designed for near real-time traffic analysis. The process is structured into two main components: Graph Generation and Anomaly Detection. | CIC-IDS2017, CIC-IDS2018, ACI-IoT2023 | it also works on autoencoder based anomaly detection using network traffic dataset. |
| 2 | | | | | | |
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
| | Library / Tool | | |

