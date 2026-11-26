# Fed-MAGNet

# Fed-MAGNet: Trust-Aware Federated Hybrid Model with Explainable AI for TON-IoT

## 📌 Overview
This repository contains the implementation of a **Multi-Agent Federated Learning** framework designed for IoT Intrusion Detection. The model is evaluated on the **TON-IoT Network Dataset** and combines a hybrid deep learning architecture with a **Trust-Aware Aggregation** mechanism to ensure robust and secure federated training.

To provide transparency, the framework includes an **Explainable AI (XAI)** pipeline featuring **Integrated Gradients** (for feature-level attribution) and **GNNExplainer** (for explanatory subgraphs and communication paths).

## ✨ Key Features
*   **Hybrid Deep Learning Architecture:**
    *   `CNN Branch`: 1D Convolutional layers for spatial feature extraction.
    *   `Adaptive Temporal Attention`: Dynamic feature re-weighting.
    *   `GAT Branch`: Graph Attention Network leveraging feature correlation as an attention mask.
    *   `Capsule Network`: Dynamic routing to class capsules (`NodeToClassCaps`) with Margin Loss for robust classification.
*   **Multi-Agent Federated Learning (5 Agents):**
    *   **Ring Topology:** Peer-to-peer communication between neighboring clients before global aggregation.
    *   **Trust-Aware Aggregation:** Agents are assigned dynamic trust scores based on update consistency (cosine similarity), loss behavior, and historical reliability (exponential moving average).
*   **Explainable AI (XAI):**
    *   **Integrated Gradients (IG):** Computes feature-level attributions to understand global and per-class feature importance.
    *   **GNNExplainer:** Learns soft edge masks over the feature-correlation graph to extract explanatory subgraphs and communication paths.
    *   **Combined Contribution Summary:** Merges IG and GNN importance into High/Medium/Low contribution labels.

## 📊 Dataset
The code is configured to run on the **TON-IoT Network Dataset**.
*   **Input File:** `train_test_network.csv`
*   **Features Used:** 34 (after dropping high-cardinality columns like `dns_query`, `ssl_subject`, etc.)
*   **Classes:** 10 (backdoor, ddos, dos, injection, mitm, normal, password, ransomware, scanning, xss)
*   **Data Balancing:** The training set is balanced using **SMOTE** before being partitioned into 5 agents.

## 🛠️ Requirements & Installation
Ensure you have Python 3.8+ installed. Install the required dependencies:

```bash
pip install tensorflow scikit-learn imbalanced-learn pandas numpy matplotlib seaborn networkx
