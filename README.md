# ⚒️ RiskForge
> A local, AI-augmented risk register assistant that forges raw threats into audit-ready, actionable insights.

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Python](https://img.shields.io/badge/python-3.11+-blue)
![Compliance](https://img.shields.io/badge/compliance-ISO%2027001%20%7C%20NIST%20CSF-green)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## 🎯 Problem

Risk registers are a core requirement of frameworks like ISO 27001 and NIST CSF - yet in practice they are often maintained as static spreadsheets: manually updated, inconsistently formatted, and prone to gaps. Shadow IT assets go untracked, controls are left unassigned, and audit trails are incomplete.

**RiskForge solves this** by enforcing structure, validation, and accountability at the point of risk intake.

---

## 💡 Solution

RiskForge is a locally-run GRC tool built for security analysts who need audit-ready risk registers without enterprise tooling overhead.

| Feature | Description |
|---|---|
| **CMDB-backed validation** | Only accepts risks against known assets - unknown assets are flagged as Shadow IT |
| **Shadow IT triage** | Unrecognised assets enter a separate triage queue for investigation |
| **Human-in-the-loop approval** | Four-eyes principle enforced - risks require peer review before registration |
| **Local LLM augmentation** | On-device AI suggests controls, scores impact, and enriches risk fields |
| **Inherent / Residual scoring** | Likelihood × Impact matrix aligned to ISO 27001 risk methodology |
| **Compliance export** | Audit-ready exports tagged with approver identity and timestamp |

---

## 🔁 Workflow

```
Analyst submits risk
        │
        ▼
┌───────────────┐     Unknown asset?     ┌──────────────────┐
│  CMDB Check   │ ────────────────────▶ │  Shadow IT Queue │
└───────────────┘                        └──────────────────┘
        │ Known asset
        ▼
┌───────────────┐
│ Triage Queue  │  ◀──── Local AI enriches risk (controls, score)
└───────────────┘
        │ GRC peer review
        ▼
┌───────────────┐
│   Approval    │  ◀──── Four-eyes sign-off
└───────────────┘
        │
        ▼
┌──────────────────────┐
│ Audit-Ready Register │  Tagged: approver + timestamp
└──────────────────────┘
        │
        ▼
  Export Report
```

---

## 📂 MVP Features

- [x] Data models: Risk, Asset, CMDB (Pydantic + SQLModel)
- [ ] Asset validation against local CMDB
- [ ] Shadow IT triage queue
- [ ] Inherent / Residual risk scoring engine
- [ ] Human-in-the-loop approval workflow
- [ ] Streamlit UI (intake form, triage queue, audit register)
- [ ] Local LLM integration via Ollama
- [ ] Compliance export (CSV / PDF)

---

## 🏗️ Project Structure

```
riskforge/
├── app.py                  # Entry point
├── requirements.txt
├── data/
│   └── riskforge.db        # SQLite database
├── riskforge/
│   ├── models/             # Pydantic data models
│   │   ├── risk.py
│   │   └── asset.py
│   ├── db/                 # SQLModel table definitions + DB logic
│   ├── core/               # Business rules (scoring, validation, workflow)
│   ├── ai/                 # Local LLM integration (Ollama)
│   └── ui/                 # Streamlit interface
└── exports/                # Generated compliance reports
```

---

## 📜 Compliance Alignment

| Framework | Control |
|---|---|
| ISO 27001 | Section 6.1 - Information Security Risk Assessment |
| NIST CSF | Identify (ID.RA) - Risk Assessment |
| NIST CSF | Protect (PR.IP) - Information Protection Processes |

---

## 🔮 Future Enhancements

- **Asset relationship graph** - model ports, IPs, roles, and dependencies between assets
- **Blast radius analysis** - AI traversal of asset relationships to assess cascading risk
- **CMDB sync** - import asset inventory from external sources (CSV, API)
- **Risk trend dashboard** - track residual risk reduction over time

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.11+ |
| Data validation | Pydantic v2 |
| Database ORM | SQLModel + SQLite |
| UI | Streamlit |
| Local AI | Ollama |
| Export | CSV / ReportLab (PDF) |

