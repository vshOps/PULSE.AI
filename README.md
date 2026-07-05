<div align="center">

<br/>

<img width="120" src="https://img.shields.io/badge/PULSE-Care%20OS-7c6af7?style=for-the-badge&logo=heart&logoColor=white"/>

<br/>
<br/>

# PULSE.AI
Predictive Unified Lifecycle System for Everyone — AI That Keeps Doctors and Patients Connected Between Every Visit

*An AI-powered Care Operating System that eliminates the gap between doctor visits*

<br/>

![Status](https://img.shields.io/badge/Status-Active-4fd1a5?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-7c6af7?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-f5a623?style=flat-square)
![AI Powered](https://img.shields.io/badge/AI-Powered-e85d75?style=flat-square)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

<br/>

[View Demo](#) • [Report Bug](https://github.com/vshOps/PULSE/issues) • [Request Feature](https://github.com/vshOps/PULSE/issues)

</div>

---

## The Problem

> Healthcare does not fail inside the clinic. It fails in the silence between visits.

India has **77 million diabetic patients** and only **1 doctor for every 1456 patients**. A typical consultation lasts **8 to 10 minutes**, once every 3 months.

```
Patient leaves clinic → forgets medication → stress builds silently →
warning signs appear → nobody is watching → Preventable Emergency
```

Every existing healthcare app digitizes the clinic visit. **PULSE uses AI to eliminate the gap between visits.**

---

## What is PULSE?

PULSE is an **AI-native Care Operating System**. Every core feature is powered by a distinct AI model working continuously in the background — not as a chatbot bolted onto a form, but as the actual engine driving every decision, alert, and recommendation in the system.

---

## How PULSE Uses AI — The Engine Under the Hood

PULSE runs **4 specialized AI models** working together, each solving a different problem:

```
┌─────────────────────────────────────────────────────────────────┐
│                        PULSE AI ENGINE                          │
├───────────────────┬───────────────────┬─────────────────────────┤
│  MODEL 1           │  MODEL 2          │  MODEL 3                │
│  Scoring Model      │  Causal Inference │  Speech + Emotion Model │
│  (Regression /      │  Model (Bayesian  │  (NLP + Audio           │
│   Weighted ML)       │  Network / Graph) │   Classification)      │
├───────────────────┴───────────────────┴─────────────────────────┤
│  MODEL 4                                                         │
│  Predictive Risk Model (Time-Series Forecasting / LSTM)         │
└───────────────────────────────────────────────────────────────────┘
```

---

### AI Model 1 — Mirror Score Engine

**Type:** Weighted multi-input regression model

**What it does:** Continuously ingests data from 5 different sources and outputs a single score from 0–100.

```
INPUTS                          MODEL                    OUTPUT
─────────────────────────────────────────────────────────────────
Wearable vitals (BP, HR)   ─┐
Lab results (HbA1c, LDL)   ─┤
Sleep + mood check-ins     ─┼──▶  Weighted Scoring   ──▶  Mirror
Medication pickup logs     ─┤     Model (per-patient        Score
Family/social check-ins    ─┘     calibrated weights)        0-100
```

The model is **personalized per patient** — weights are recalibrated over time based on which factors historically preceded that specific patient's health decline. This is not a static formula; it is a model that learns each patient's unique risk pattern.

---

### AI Model 2 — Causal Chain Inference Engine

**Type:** Bayesian causal graph / probabilistic reasoning model

**What it does:** This is the core innovation of PULSE. Instead of just flagging correlated symptoms, this model builds a **directed causal graph** — the same class of technique used in epidemiology — to infer which event *triggered* which downstream effect.

```
                     ┌─────────────────────┐
   Raw Signals  ───▶ │  Causal Graph Model │ ───▶  Root Cause + Chain
                     │  (Bayesian Network)  │
                     └─────────────────────┘
                              │
              Learns from thousands of prior
              patient trajectories which signal
              sequences reliably predict which
              outcomes — then applies that graph
              to this patient's live data
```

Example output:
```
P(BP_rise | stress_spike, sleep_disruption) = 0.81
→ System flags: "Root cause is likely stress-driven, not primary hypertension"
```

This lets the doctor treat causes instead of symptoms — something no rule-based or purely statistical dashboard can do.

---

### AI Model 3 — Emotion-Aware Ambient Scribe

**Type:** Speech-to-text (ASR) + NLP summarization + audio emotion classification, running as a real-time pipeline

**What it does:** Three AI subsystems run in parallel during every consultation:

```
Doctor-Patient Audio Stream
         │
         ├──▶ [ASR Model] ──▶ Live transcript
         │
         ├──▶ [Clinical NLP Summarizer] ──▶ Structured SOAP note
         │        (extracts symptoms, diagnosis, plan from transcript)
         │
         └──▶ [Emotion Classifier] ──▶ Real-time emotional state
                  (analyzes tone, pace, word choice — not just words)
                          │
                          ▼
              Alert doctor if patient shows
              fear / confusion / denial signals
```

After the consultation, a **translation model** converts the generated care plan into the patient's regional language before it is sent via WhatsApp — closing the loop between what the AI understood and what the patient actually receives.

---

### AI Model 4 — Predictive Risk Radar

**Type:** Time-series forecasting model (sequence model trained on longitudinal patient data)

**What it does:** Takes a patient's historical trend data — vitals, labs, adherence — as a sequence, and forecasts the probability of specific future events within a defined time window.

```
Historical sequence (12 weeks of data)
         │
         ▼
┌─────────────────────┐
│  Sequence Model      │ ───▶  P(cardiac event within 4 months) = 67%
│  (LSTM / Temporal     │ ───▶  P(insulin dependency within 6mo) = 41%
│   Transformer)        │ ───▶  P(neuropathy within 12mo) = 18%
└─────────────────────┘
         │
         ▼
Each prediction is paired with the specific
input features that drove it (explainability layer)
```

This model is what shifts PULSE from **reactive** care to **preventive** care — it doesn't wait for lab results to confirm a problem, it forecasts the problem before it fully develops.

---

## The Complete AI Data Flow

```
                         ┌──────────────────────┐
                         │   DATA COLLECTION      │
                         │  Wearables · Labs ·    │
                         │  Check-ins · Pharmacy   │
                         └──────────┬─────────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    ▼               ▼               ▼
          ┌─────────────────┐ ┌───────────┐ ┌─────────────────┐
          │  Mirror Score    │ │  Causal   │ │  Predictive Risk │
          │  Model           │ │  Engine   │ │  Model            │
          └────────┬─────────┘ └─────┬─────┘ └────────┬─────────┘
                   │                 │                │
                   └────────────────┬┴────────────────┘
                                    ▼
                         ┌──────────────────────┐
                         │   DOCTOR DASHBOARD     │
                         │  Unified AI Insights   │
                         └──────────┬─────────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │  Ambient Scribe AI     │
                         │  (during consultation) │
                         └──────────┬─────────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │  Translation + WhatsApp│
                         │  Delivery to Patient   │
                         └────────────────────────┘
```

---

## Why This AI Architecture is Different

| Typical Health AI Apps | PULSE |
|---|---|
| Single chatbot answering questions | 4 specialized models solving 4 distinct problems |
| Shows correlation ("BP is high") | Shows causation ("stress is causing BP to rise") |
| Static rule-based alerts | Personalized, self-calibrating scoring model |
| Generic risk scores | Time-window forecasts with explainability |
| Text-only interaction | Audio-based emotion detection during real conversations |
| One-size-fits-all output | Auto-translated, per-patient, delivered where they already are — WhatsApp |

---

## What Makes PULSE Unique

- **Continuous care, not episodic care** — AI monitors between visits, not just during them
- **Causal reasoning, not just prediction** — shows doctors *why*, not just *what*
- **Explainable AI** — every score and prediction comes with the reasoning behind it
- **Personalized models** — each patient gets their own calibrated risk profile
- **Human-centered delivery** — AI output reaches patients in their language, on WhatsApp, in plain words

---

## Application Pages

```
PULSE/
├── 📊 Dashboard      → Doctor view: Mirror Score, Causal Chain, Health Thread
├── 📱 Patient View    → Mobile-first score, daily tasks, care updates
├── 🕸️  Care Web       → Visual node diagram of the full care team
├── 🔗 Causal Chain    → Root cause explorer with intervention points
└── 📈 Analytics       → Clinic-wide metrics and risk distribution
```

---

## Tech Stack

```
Frontend
├── HTML5
├── CSS3 — Custom properties, Grid, Flexbox, Animations
└── Vanilla JavaScript — No frameworks, no dependencies

AI Layer (Conceptual / Planned Implementation)
├── Scoring Model        → Weighted regression, per-patient calibration
├── Causal Engine         → Bayesian network / probabilistic graph
├── Ambient Scribe         → ASR + Clinical NLP + Emotion classification
├── Predictive Model       → LSTM / Temporal sequence forecasting
└── Translation Layer      → Multilingual NLP for regional language delivery

Integrations (Planned)
├── WhatsApp Business API — Patient communication
├── HL7 FHIR — Electronic health record standard
└── Wearable device APIs — Real-time vitals ingestion
```

---

## Demo Patient Data

**Patient:** Neha Patel · 54 years old · Type 2 Diabetes + Hypertension

| Metric | Value | Status |
|---|---|---|
| Mirror Score | 62 / 100 | At Risk |
| Blood Pressure | 148/94 mmHg | Critical |
| HbA1c | 7.8% | Warning |
| Heart Rate | 76 bpm | Normal |
| BMI | 28.4 | Elevated |

**Causal Chain Detected:**
`Work Stress → Sleep Disruption → Cortisol Elevation → BP Rising → Glucose Instability`

**Predictive Risk Radar:**
- Cardiovascular Event — 67% — High Risk (4 month window)
- Insulin Dependency — 41% — Medium Risk (6 month window)
- Diabetic Neuropathy — 18% — Low Risk (12 month window)

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/vshOps/PULSE.git

# Navigate into the project
cd PULSE

# Open in browser
open index.html
```

---

## Roadmap

- [x] UI/UX Design System
- [x] Doctor Dashboard
- [x] Mirror Score visualization
- [x] Causal Chain Explorer
- [ ] Live AI model integration
- [ ] WhatsApp Business API integration
- [ ] Wearable device data pipeline
- [ ] Regional language translation engine
- [ ] Mobile patient app

---

## Contributing

Contributions are welcome. Please open an issue first to discuss what you would like to change.

```bash
# Fork the repo, then:
git checkout -b feature/YourFeature
git commit -m "Add YourFeature"
git push origin feature/YourFeature
# Open a Pull Request
```

---

## License

Distributed under the MIT License.

---

<div align="center">

**Built for the AMD Ryzen Slingshot Ideathon**

*"Right now healthcare is a series of 10-minute moments separated by months of silence. PULSE turns that silence into the most important part of care."*

<br/>

Made by [**vshOps**](https://github.com/vshOps)

</div>
