# SOC Alert Pipeline: Binary + Multi-class Intrusion Detection

An end-to-end SOC (Security Operations Center) alert pipeline that:
- Detects network intrusions using a binary model
- Classifies attack types using a multi-class model
- Assigns RAG (Red/Amber/Green) and Severity levels
- Generates SOC playbook recommendations
- Provides human-readable alerts for SOC analysts

The project is deployed on Hugging Face and is free to use for testing and learning purposes.

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Demo / Hugging Face Deployment](#demo--hugging-face-deployment)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Data Files](#data-files)
7. [License](#license)

## Features

- **Binary Attack Detection:** Classifies network logs as normal or attack
- **Multi-class Attack Classification:** Provides specific attack types and confidence
- **RAG & Severity:** Prioritizes alerts for SOC analysts
- **SOC Playbook:** Suggests recommended actions based on alert severity
- **Deployment-ready:** Outputs structured DataFrame or CSV, also generates readable alert text
- **Modular & Tunable:** Thresholds and playbooks can be adjusted easily
  
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

## **6️⃣ Usage**
1. Place your network log CSV in the `data/` folder
2. Run the main script:
```bash
python src/soc_pipeline.py
````
## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

