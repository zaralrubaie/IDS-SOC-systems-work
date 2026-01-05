# SOC system overview 

A Security Operations Center (SOC) is a centralized team responsible for monitoring, detecting, analyzing, and responding to cybersecurity threats in real time.

## Typical SOC Challenges
- High volume of alerts
- Alert fatigue (too many low-quality alerts)
- Slow prioritization of real threats
- Lack of automated response guidance
---
This project addresses these challenges by automating:
- Intrusion detection
- Attack classification
- Alert prioritization
- SOC playbook recommendations
  
# SOC Alert Pipeline: Binary + Multi-class Intrusion Detection
An end-to-end SOC (Security Operations Center) alert pipeline that:
- Detects network intrusions using a binary model
- Classifies attack types using a multi-class model
- Assigns RAG (Red/Amber/Green) and Severity levels
- Generates SOC playbook recommendations
- Provides human-readable alerts for SOC analysts
  
# System Architecture & Workflow
### System Workflow

Network Traffic Logs  
⬇️  
Binary Classification (Attack vs Normal)  
⬇️  
Normal Traffic → Green / Low Severity  
⬇️  
Multi-class Classification (Attack Type Prediction)  
⬇️  
Confidence Scoring (Binary + Multi-class)  
⬇️  
RAG & Severity Assignment (Red / Amber / Green)  
⬇️  
SOC Playbook Mapping  
⬇️  
Human-readable SOC Alert

---
## Why Binary + Multi-class Models?

- Binary Classification (Attack vs Normal)
Purpose:
Quickly filters traffic into:
1. Normal
2.Attack
- Multi-class Classification (Attack Type)
Purpose:
- Identifies the type of attack, such as:
1. DoS
2. Probe
3. Exploit
4. Brute Force
5. Other intrusion categories
  
##  Alert Prioritization: RAG & Severity
The pipeline assigns:
RAG Status
- 🟥 Red – Critical threat

- 🟧 Amber – Suspicious / Medium risk

- 🟩 Green – Normal activity

 Severity Levels:
- High

- Medium

- Low

This allows SOC analysts to:

- Focus on high-risk alerts first
- Reduce alert fatigue
- Make faster decisions

## Features

- **Binary Attack Detection:** Classifies network logs as normal or attack
- **Multi-class Attack Classification:** Provides specific attack types and confidence
- **RAG & Severity:** Prioritizes alerts for SOC analysts
- **SOC Playbook:** Suggests recommended actions based on alert severity
- **Deployment-ready:** Outputs structured DataFrame or CSV, also generates readable alert text
- **Modular & Tunable:** Thresholds and playbooks can be adjusted easily
  
##  Example Output 

| Attack Type | Binary Confidence | Multi-class Confidence | RAG   | Severity |
| ----------- | ----------------- | ---------------------- | ----- | -------- |
| DoS         | 0.94              | 0.35                   | Red   | High     |
| Probe       | 0.93              | 0.36                   | Red   | High     |
| Normal      | 0.98              | —                      | Green | Low      |

. Human-Readable SOC Alert

ALERT: Potential DoS attack detected
Severity: High (Red)
Confidence: 94%

Recommended Actions:
- Investigate source IP
- Apply temporary network block
- Escalate to Tier 2 SOC analyst

---
## Demo / Hugging Face Deployment

You can try the live version of this pipeline here:  
[Hugging Face SOC Alert Demo]((https://huggingface.co/spaces/zahraa12355/soc))

**How to use the demo:**

1. **Enter network parameters manually** in the input fields:
   - `dur`, `spkts`, `dpkts`, `sbytes`, `dbytes`, `rate`
   - `sttl`, `dttl`, `sload`, `dload`
2. Click **Submit / Run** to get predictions.
3. Outputs displayed:
   - **Binary Prediction** (attack or normal)
   - **Multi-class Prediction** (specific attack type)
   - **Confidence Scores**
   - **RAG / Severity**
   - **Recommended SOC Playbook Actions**
  
     ## Installation

1. Clone the repository:
```bash
git clone https://github.com/zaralrubaie/soc-alert-pipeline.git
cd soc-alert-pipeline
````
2. Create a virtual environment
- python -m venv venv
- source venv/bin/activate  # Linux/Mac
- venv\Scripts\activate     # Windows
  
3. Install dependencies:
````
pip install -r requirements.txt
````
---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

