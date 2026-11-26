## 📊 Datasets

The Fed-MAGNet framework is evaluated using two cybersecurity datasets to investigate the robustness, generalization, and reliability of trust-aware federated intrusion detection across heterogeneous IoT environments.

### 1. TON-IoT Network Dataset

- **Input File:** `train_test_network.csv`
- **Features Used:** 34 selected network traffic features.
- **Classes:** 10 (backdoor, ddos, dos, injection, mitm, normal, password, ransomware, scanning, xss).
- **Data Balancing:** SMOTE applied to the training set.
- **Federated Configuration:** Data partitioned among 5 agents.
- **Evaluation:** Multiclass intrusion detection and trust-aware federated aggregation.

### 2. CIC IoMT Dataset 2024

- **Dataset:** CIC IoMT Dataset 2024.
- **Official Source:** https://www.unb.ca/cic/datasets/iomt-dataset-2024.html
- **Environment:** Internet of Medical Things (IoMT).
- **IoMT Devices:** 40 devices (25 real and 15 simulated).
- **Protocols:** Wi-Fi, MQTT, and Bluetooth Low Energy (BLE).
- **Attack Categories:** DDoS, DoS, Recon, MQTT, and Spoofing.
- **Attack Scenarios:** 18 different cyberattack scenarios.
- **Data Formats:** CSV feature files and original PCAP network traffic files.
- **Data Preprocessing:** Data cleaning, missing-value handling, categorical encoding, feature selection, and normalization.
- **Federated Configuration:** Distributed data partitioning among 5 agents.
- **Evaluation:** Multiclass IoMT intrusion detection, federated learning performance, and trust-aware aggregation.

### Dataset Integration Strategy

Both datasets are processed independently using dataset-specific preprocessing and feature configurations. The same Fed-MAGNet architecture, trust-aware aggregation strategy, and explainable AI framework are used to evaluate their respective intrusion detection tasks.

The framework uses Integrated Gradients for feature-level explanations and GNNExplainer for graph-based explanations.

**Important:** The two datasets have different feature spaces and attack labels. Separate classification heads or dataset-specific model configurations should be used where necessary. Their raw features should not be directly merged.
