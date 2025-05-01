
# 🧠 Agentic Medical AI — OSCE Case Diagnosis

This project showcases a multi-agent reasoning system designed to simulate medical OSCE (Objective Structured Clinical Examination) scenarios. The AI agents—Doctor, Patient, Measurement, and Moderator—interact in a structured conversation to assess, reason, and arrive at a medical diagnosis.

## 🚀 Features

- 👨‍⚕️ Doctor agent reasoning over patient history, symptoms, and tests.
- 🗣️ Simulated patient responding with scenario-specific context.
- 📊 Measurement agent that provides test results when queried.
- 👥 Moderator that ensures structured, step-wise diagnostic reasoning.
- ✅ Final diagnosis with correctness check against ground truth.
- 💬 Streamlit UI with interactive chat-based conversation layout.
- 📁 Upload your own scenario or use a prefilled sample OSCE case.

---

## 🛠️ Installation

```bash
  git clone https://github.com/koteshb25/AgenticMedicalAi.git 

cd AgenticMedicalAi

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt
```

---

## 🧪 Running the App

```bash
streamlit run ui.py
```

---

## 🧾 How It Works

1. Choose between:
   - ✅ Pre-filled sample OSCE scenario
   - 📁 Upload a custom JSON scenario file

2. Click **"Run Agent Diagnosis"** — the multi-agent system starts interacting:

    - **Doctor Agent** leads the consultation.
    - **Patient Agent** responds with symptom history.
    - **Measurement Agent** provides physical and test results when prompted.
    - **Moderator Agent** ensures a structured diagnostic flow.

3. The system then:
   - Presents the **final diagnosis**
   - Displays a **chat-based conversation UI** between agents
   - Shows full **reasoning logs**
   - Compares the final diagnosis with the ground truth

---

## 📊 Sample Input Format

Example OSCE scenario JSON structure:

```json
{
  "OSCE_Examination": {
    "Objective_for_Doctor": "Assess patient with double vision...",
    "Patient_Actor": {
      "Demographics": "35-year-old female",
      "History": "...",
      "Symptoms": {
        "Primary_Symptom": "...",
        "Secondary_Symptoms": ["...", "..."]
      },
      ...
    },
    "Physical_Examination_Findings": { ... },
    "Test_Results": { ... },
    "Correct_Diagnosis": "Myasthenia gravis"
  }
}
```

---

## 🤖 Technologies Used

- **Python**
- **Streamlit** for interactive UI
- **Gemini 2.0 Flash** API for all LLM agents (Doctor, Patient, etc.)
- Modular multi-agent architecture in `agentclinic/`

---

## 🔐 API Keys

Set your API keys inside the app before running the diagnosis:

```python
gemini_api_key = "YOUR_GEMINI_API_KEY"
openai_api_key = None
anthropic_api_key = None
```

---

## 📂 Project Structure

```
AgenticMedicalAi/
│
├── ui.py                        # Streamlit UI
├── agentclinic/
│   └── agentclinic.py                # Core agent execution logic
│   └── agents/                   # Doctor, Patient, etc.
│   └── scenarios/                # Sample and custom scenario loaders
│
├── requirements.txt
└── README.md
```

---

## 📸 Screenshot

![UI Screenshot](docs/sample_ui.png)

---

## 📌 TODOs

- [ ] Add voice-to-text input for patient symptoms
- [ ] Expand dataset with more OSCE-style cases
- [ ] Integrate final feedback summary with confidence scores


## 📄 License

This project is licensed under the MIT License.
