# Cognitive Attack Topology (CAT) Framework

[![Research](https://img.shields.io/badge/Research-Elite-gold.svg)](#) 
[![Build-Status](https://img.shields.io/badge/Sprint-41h_37m-red.svg)](#) 
[![Model-Performance](https://img.shields.io/badge/ROC--AUC-0.955-green.svg)](#)
[![Field](https://img.shields.io/badge/Field-Cognitive_Topological_Cybersecurity-blue.svg)](#)

> **"Mapping the geometry of human-targeted cyber attacks."**

Traditional cybersecurity focuses on protecting networks, endpoints, and the cloud. However, modern fraud bypasses firewalls to attack **human cognition directly.** The **CAT Framework** introduces a new paradigm: Cyber attacks are not just malicious payloads; they are **topological transformations of human trust networks.**

---

## 🚀 The Sprint Challenge: Execution Metrics
This framework was developed during a high-intensity research sprint, moving from theoretical derivation to a validated benchmarked architecture.

| **Metric** | **Target** | **Achievement** |
| :--- | :--- | :--- |
| **Architect** | Enterprise Research Team | **Dhadi Sai Praneeth Reddy (Solo)** |
| **Time Limit** | 72 Hours | **41 Hours 37 Minutes (Finished Early)** |
| **Status** | Implementation Phase | **Mission Accomplished** |
| **Outcome** | POC to Validated Framework | **GCT-100k Dataset + 11 Research Notebooks** |

---

## 🏛️ New Research Field: Cognitive Topological Cybersecurity (CTC)

**Definition:** The study of cyber attacks as topological distortions in human-digital interaction graphs.

In this paradigm, an interaction is not a static event but a geometric manifold. The **CAT Framework** identifies attacks by measuring the stress and warp applied to this manifold when an attacker attempts to hijack the "trust-vector" of a legitimate entity (e.g., a Bank or Government Agency).

---

## 📐 Mathematical Framework

### 1. Trust Topology Tensor (TTT)
Human-digital interactions are represented as a high-dimensional tensor:
$$T_{ijk}$$
Where:
* **$i$**: User Identity (Target)
* **$j$**: Communication Channel (Audio, SMS, WhatsApp, Email)
* **$k$**: Trust Signal Primitives (Authority Claim, Urgency, Emotional Pressure)

### 2. Cognitive Distortion Energy (CDE)
We quantify the intensity of an attack by calculating the energy required to distort a user's baseline trust graph:
$$CDE = \sum_{i,j,k} \omega_{ijk} T_{ijk}$$
Where $\omega$ represents weights assigned to specific psychological manipulation tactics.

### 3. Trust Distortion Index (TDI)
Normalizing the attack energy against the standard trust variance ($\sigma$) of the environment:
$$TDI = \frac{CDE}{\sigma_{trust}}$$
* **High TDI**: Indicates a high probability of a "Cloaked" attack.

### 4. Cognitive Manipulation Score (CMS)
A weighted aggregation of psychological pressure points:
$$CMS = \alpha U + \beta F + \gamma A + \delta P$$
*(U: Urgency, F: Fear, A: Authority, P: Persuasion)*

---

## 🛠️ System Architecture (The CAT Engine)

1.  **Signal Capture Layer**: Ingests multi-channel inputs (Phone audio, SMS, Chat) and decomposes them into psychological primitives using Transformer-based embeddings.
2.  **Topological Mapper**: Constructs a dynamic interaction graph. Nodes represent users and institutions; edges represent communication flows and trust weights.
3.  **Distortion Analyzer**: Executes the **TMD (Topological Manipulation Detection)** algorithm to identify anomalies where an external node attempts to kolonize the centrality of a trusted node.
4.  **Intervention Engine**: Provides autonomous responses based on TDI thresholds, ranging from silent warnings to real-time transaction blocking.

---

## 🌍 The GCT-100k Dataset
The **Global Cognitive Threat Dataset** is a high-fidelity benchmark consisting of **100,000 samples** designed to evaluate AI models on human-targeted deception.

### Dataset Composition
* **Real-world Anonymized (40%)**: Actual intercepted fraud attempts.
* **Public Datasets Merged (30%)**: Standardized NLP security data.
* **Synthetic Attack Generation (30%)**: Adversarial samples designed to bypass traditional filters.

### Elite Schema (30+ Features)
| Category | Key Features |
| :--- | :--- |
| **Psychological** | `fear_trigger_score`, `cognitive_load_score`, `persuasion_strategy` |
| **Communication** | `urgency_score`, `authority_claim`, `interaction_entropy` |
| **Technical** | `ip_address_hash`, `malicious_domain_score`, `network_type` |
| **Ground Truth** | `human_verified_label`, `cognitive_distortion_score` |

---

## 📈 Results & Benchmarking

### 1. Comparative Performance (Notebook 08)
The CAT_Model (utilizing the Cognitive Tensor) outperformed all traditional text-based baselines.

| Model | Feature Set | ROC-AUC | Accuracy | F1-Score | Precision | Recall |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Logistic Regression | Text | 0.7440 | 0.6674 | 0.6604 | 0.6663 | 0.6546 |
| RandomForest | Text | 0.9283 | 0.8120 | 0.8070 | 0.8186 | 0.7957 |
| XGBoost | Text | 0.8146 | 0.7016 | 0.6110 | 0.8579 | 0.4744 |
| **CAT_Model** | **Cognitive Tensor** | **0.9555** | **0.8508** | **0.8479** | **0.8537** | **0.8422** |

### 2. Adversarial Robustness (Notebook 09)
We evaluated the framework's resistance to "Cloaking" and "Obfuscation" tactics.
* **Baseline AUC**: 0.8845
* **Robustness Score**: **0.9258**
* **Insight**: The model demonstrated exceptional performance in **Multilingual Scams (0.984 AUC)**, proving that topological signals are language-agnostic.

### 3. Final Hybrid Validation (Notebook 11)
| Model | Task | ROC-AUC | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CAT_Hybrid** | **Scam Detection** | **0.9415** | **0.8325** | **0.8278** | **0.8302** |
| RandomForest | Scam Detection | 0.9108 | 0.8118 | 0.7663 | 0.7884 |
| SVM | Scam Detection | 0.6596 | 0.6597 | 0.6421 | 0.6508 |

---

## 🛡️ Trust Preservation Metrics
* **Attack Prevention Rate (APR)**: 53.28% (Initial Simulation)
* **Trust Preservation Score (TPS)**: 0.6934
* **False Positive Rate (FPR)**: Managed via TDI thresholding to ensure legitimate institutional communication is not disrupted.

---

## 🧑‍💻 Author & Lead Researcher
**Dhadi Sai Praneeth Reddy** *Specializing in High-Velocity AI/ML Engineering & Cognitive Security Architectures.*

---
*Developed under the guidance of Dr. M. Jithender Reddy. Part of the CAT Research Publication Series - March 2026.*
