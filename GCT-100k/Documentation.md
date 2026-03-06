# GCT-100K  
**Global Cognitive Threat Dataset**  
*A Benchmark Dataset for Human-Targeted Cyber Manipulation Detection*

---

## Overview

The **Global Cognitive Threat Dataset (GCT‑100K)** is a research‑grade benchmark dataset designed to study and detect **human‑targeted cyber attacks** that exploit **psychological manipulation** rather than pure technical vulnerabilities. These include phishing, OTP fraud, bank impersonation, social engineering chats, and financial scams.

Modern cybersecurity systems focus heavily on network, endpoint, and cloud‑based threats. However, a growing proportion of attacks targets **human cognition directly**, using emotional triggers such as:

- **Urgency**
- **Fear**
- **Authority**  
- **Reward**

GCT‑100K encodes these cognitive manipulations alongside technical indicators, enabling machine learning models to detect **trust‑topology‑level** manipulation in human‑digital interactions.

The dataset is designed to support research in:

- AI‑driven cyber threat detection  
- Social engineering analysis  
- Human‑centric cybersecurity  
- Behavioral threat modeling  
- Cognitive manipulation‑aware fraud detection

---

## Dataset Composition

| Source              | Percentage | Description |
|---------------------|-----------|------------|
| Real‑world anonymized | 40% | Aggregated and anonymized cybersecurity communication samples from real-world fraud logs. |
| Public datasets      | 30% | Merged phishing, SMS spam, and scam‑call corpora from existing public datasets. |
| Synthetic generation | 30% | AI‑generated interaction samples designed to simulate emerging attack patterns and expand coverage. |

This 40/30/30 mixture ensures:

- **Realism** through real‑world communication logs  
- **Diversity** via public datasets  
- **Future‑attack coverage** via synthetic data

---

## Dataset Categories

| Category                   | Description |
|----------------------------|-----------|
| Scam Calls                 | Bank / OTP fraud, fake customer‑support calls, and phone‑based financial scams. |
| Phishing SMS               | SMS messages containing malicious links or fake offers. |
| Social Engineering Chats   | Conversations designed to manipulate trust, urgency, or fear (e.g., WhatsApp, Telegram, email). |
| Legitimate Conversations   | Non‑malicious baseline conversations used for modeling “normal” behavior. |
| Financial Fraud Scripts    | Message scripts targeting payment redirection or financial extraction (UPI, cards, wallets, etc.). |

---

## Dataset Size

| Version        | Samples      |
|----------------|-------------|
| GCT‑Phase1     | 100,000     |
| **Full GCT‑19M (target)** | 19,734,289 |

`GCT‑Phase1` (100K) is a manageable, research‑ready subset of the full GCT‑19M scale, suitable for training and benchmarking.

---

## Files Included

- `GCT_phase1_100k.csv` (58.63 MB) – Human‑readable CSV, 100,000 rows, 30+ columns.  
- `GCT_phase1_100k.parquet` (13.66 MB) – Compressed Parquet, ideal for fast loading with `pandas` / `PyArrow`.

Use CSV for quick inspection and debugging; use Parquet for large‑scale training and experimentation.

---

## Data Dictionary (Summary)

| Column Name | Type | Scale | Description |
|------------|------|------|------------|
| `interaction_id` | UUID | Nominal | Unique identifier for each interaction. |
| `timestamp` | `ISO-8601 datetime` | Interval | Time when the interaction occurred. |
| `country_code` | Categorical | Nominal | ISO‑3166 country code. |
| `language` | Categorical | Nominal | Detected language of the message. |
| `channel` | Categorical | Nominal | Communication medium (e.g., call, SMS, email, chat). |
| `platform` | Categorical | Nominal | Messaging platform (e.g., WhatsApp, Telegram, SMS, email client). |
| `text_transcript` | Text | N/A | Full text of the conversation or message. |
| `audio_features` | Float Vector | Ratio | Embeddings extracted from audio (phone calls). |
| `sentiment_score` | Float | Interval | Emotional polarity (e.g., positive / negative). |
| `urgency_score` | Float | Ratio | Level of urgency pressure (0–1). |
| `authority_claim` | Boolean | Nominal | Whether the message impersonates a bank, government, or authority. |
| `fear_trigger_score` | Float | Ratio | Strength of fear‑based manipulation (0–1). |
| `trust_manipulation_score` | Float | Ratio | Intensity of trust exploitation (0–1). |
| `cognitive_load_score` | Float | Ratio | Psychological pressure on the user (0–1). |
| `persuasion_strategy` | Categorical | Nominal | Type of persuasion tactic (e.g., scarcity, reward, social proof). |
| `social_engineering_pattern` | Categorical | Nominal | Attack sequence pattern (e.g., reconnaissance → extraction). |
| `ip_address_hash` | String | Nominal | SHA‑256‑hashed IP address, anonymized. |
| `device_type` | Categorical | Nominal | Device class (phone, PC, tablet, etc.). |
| `network_type` | Categorical | Nominal | Connection type (mobile, Wi‑Fi, broadband, etc.). |
| `url_domain` | String | Nominal | Domain extracted from links. |
| `malicious_domain_score` | Float | Ratio | Model‑estimated probability of domain being malicious (0–1). |
| `response_time` | Float | Ratio | Time (seconds) between user responses. |
| `message_frequency` | Integer | Ratio | Number of messages in the interaction. |
| `conversation_length` | Integer | Ratio | Number of characters in the transcript. |
| `interaction_entropy` | Float | Ratio | Shannon entropy of the conversation text. |
| `attack_type` | Categorical | Nominal | Attack category (e.g., OTP_fraud, phishing, social_engineering, legitimate). |
| `attack_stage` | Categorical | Ordinal | Attack progression (e.g., reconnaissance, extraction, persuasion). |
| `attack_complexity` | Ordinal | Ordinal | Low / medium / high complexity. |
| `financial_target` | Integer | Ratio | Amount (rupees / dollars) targeted in the fraud. |
| `trust_signals` | Float | Ratio | Composite trust‑signal score. |
| `cognitive_distortion_score` | Float | Ratio | Overall manipulation / cognitive distortion level (0–1). |
| `human_verified_label` | Boolean | Nominal | Human‑verified ground‑truth label (0/1). |
| `model_prediction` | Boolean | Nominal | AI model’s prediction (0/1). |
| `confidence_score` | Float | Ratio | Model confidence (0–1). |

---

## Attribute Deep‑Dive

### interaction_id

- **Semantic Definition**: A globally unique identifier representing a single communication interaction.
- **Type**: UUID  
- **Scale**: Nominal  
- **Domain Constraints**: Must be globally unique.  
- **Nullity Strategy**: Missing values indicate corrupted records and should be discarded.  
- **Research Significance**: Enables reproducible indexing and traceability of interactions.  
- **Edge Cases**: Duplicate IDs may indicate dataset‑merging errors.

### timestamp

- **Semantic Definition**: Time at which the interaction occurred.  
- **Type**: `ISO‑8601 datetime`  
- **Scale**: Interval  
- **Domain Constraints**: Must follow ISO‑8601 format.  
- **Nullity Strategy**: Missing values can be imputed using session order or removed.  
- **Research Significance**: Critical for temporal pattern detection (e.g., time‑based phishing spikes).  
- **Edge Cases**: Time‑zone inconsistencies must be normalized before modeling.

### urgency_score

- **Semantic Definition**: Quantifies the degree of urgency expressed in the message.  
- **Type**: Float  
- **Scale**: Ratio  
- **Range**: 0–1  
- **Constraints**: 0 = no urgency, 1 = extreme urgency.  
- **Research Significance**: Urgency is a primary driver of phishing and OTP‑fraud success.  
- **Edge Cases**: Legitimate banking alerts may also show high urgency; this must be modeled carefully.

### authority_claim

- **Semantic Definition**: Indicates whether the sender impersonates authority (bank, police, government, etc.).  
- **Type**: Boolean  
- **Scale**: Nominal  
- **Research Significance**: Authority‑based manipulation is one of the most powerful social‑engineering tactics.

### interaction_entropy

- **Semantic Definition**: Measures randomness in the text using Shannon entropy.  
- **Formula**:
$$H = -\sum_{i=1}^{n} p(x_i) \log p(x_i)$$
- **Type**: Float  
- **Scale**: Ratio  
- **Research Significance**: Scam scripts often show **lower entropy** due to predictable templates and repeated phrases.

### cognitive_distortion_score

- **Semantic Definition**: A composite score estimating the strength of **psychological manipulation** in the interaction.  
- **Research Significance**: Acts as a core predictor of cyber fraud success and human‑targeted attack intensity.

---

## Cognitive Manipulation Score (CMS)

The dataset introduces a composite metric:

$$\text{CMS} = \alpha U + \beta F + \gamma A + \delta P$$

Where:

| Variable | Meaning |
|---------|---------|
| `U`     | Urgency score |
| `F`     | Fear trigger score |
| `A`     | Authority claim (as numeric 0/1) |
| `P`     | Persuasion strength (encoded from `persuasion_strategy`) |

CMS can be used directly as:

- A **feature** for fraud detection,  
- A **target signal** for ranking manipulation intensity,  
- Or a **benchmark metric** for evaluating cognitive‑aware models.

---

## Privacy and Anonymization

To ensure ethical and privacy‑compliant reuse, all sensitive attributes have been protected via:

- **SHA‑256 hashing** of identifiers (including `ip_address_hash`)  
- **Removal of phone numbers**  
- **Removal of personal names**  
- **Domain‑based anonymization**  
- **Synthetic augmentation** of sensitive patterns  

**No personally identifiable information (PII)** is included in the dataset. All real‑world samples are anonymized before inclusion.

Use this dataset only for **research and defensive cybersecurity purposes**. Avoid misuse for generating real‑world social‑engineering attacks.

---

## Potential Research Applications

This dataset enables research and model development in:

- **Social engineering detection** (call‑based, chat‑based)  
- **Phishing message classification** (SMS, WhatsApp, Telegram, email)  
- **Fraud detection** (OTP scams, UPI fraud, banking fraud)  
- **Behavioral cybersecurity** modeling  
- **Trust manipulation** and cognitive‑topology analysis  
- **Cognitive‑aware AI‑based cyber defense frameworks** (e.g., CAT‑Lab‑style pipelines)

---

## Suggested Benchmark Tasks

You can use GCT‑100K for tasks such as:

- **Binary scam detection**  
  - Predict: `attack_type` in {`otp_fraud`, `phishing`, `social_engineering`} vs `legitimate`.  
- **Multi‑class attack classification**  
  - Predict detailed `attack_type` and `attack_stage`.  
- **Cognitive manipulation scoring**  
  - Regress `cognitive_distortion_score` or `CMS` using psychological and behavioral signals.  
- **Trust exploitation detection**  
  - Detect when `trust_manipulation_score` exceeds a threshold while other signals suggest risk.  
- **Temporal anomaly detection**  
  - Use `timestamp`, `response_time`, and `message_frequency` to detect unusual conversation dynamics.

---

## License

**Dataset License**:  
This dataset is released under an `Apache 2.0`
---

## Citation

If you use this dataset in your research, please cite:

Global Cognitive Threat Dataset (GCT‑100K)
Atlas AI Labs, 2026.


---