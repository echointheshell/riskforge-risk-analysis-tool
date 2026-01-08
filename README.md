# RiskForge  
_An AI-augmented, local risk register assistant for SOC & compliance teams_

## 🎯 Problem  
Manual managment of risk registers are often tedious, error prone, inconsistent, and overlooks shadow IT assets, creating gaps in compliance audits.

## 💡 Solution  
RiskForge enforces audit ready discipline with:  
- **CMDB backed validation** (Only accepts assets in the CMDB as a compliance guardrail)  
- **Shadow IT triage** (Allows risks to be added for unknown assets not in the CMDB, to be logged and triaged)  
- **Human-in-the-loop approval** (Uses the four-eyes principle to have peer reviewed acceptance and confirmation of risks)  
- **Local LLM augmentation** (Smart analysis and enrichment of risk fields)  

## 🛠️ Basic Workflow  
1. Analyst submits risk which enters **Triage Queue**  
2. Local AI model enriches risk (suggests controls, impact score)  
3. GRC team discusses risk: Click **Approve Risk**
4. Risk moves to **Audit Ready Register** tagged with who approved it and when
5. Export for compliance reports  

## 📂 Features (MVP)  
- [ ] Asset validation against local CMDB (Configuration Management Database)
- [ ] Inherent/Residual risk scoring  
- [ ] Approval workflow
- [ ] Triage Queue vs. Registered Risks

## 📜 Compliance Alignment  
- ISO 27001 (Section 6.1: Risk Assessment)  
- NIST CSF (Identify + Protect)  
