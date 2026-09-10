# Cloudora SOC Alert Triage & Incident Management

**Simulated Client Engagement | SOC Alert Triage | ServiceNow**

This repository documents my work during a simulated overnight SOC engagement for **Cloudora**, a fictional B2B HR software company.

The engagement involved investigating and triaging **12 mixed security alerts** using an evidence-based SOC triage process and documenting the investigations and incident workflow in **ServiceNow**.

The objective was to determine whether each alert represented malicious activity, legitimate business activity, duplicate activity, an escalation requiring additional response, or insufficient evidence, while assigning severity and documenting a defensible analyst decision.

## Engagement Overview

- **Organization:** Cloudora (fictional)
- **Role:** SOC Analyst
- **Engagement:** Simulated client engagement
- **Alerts Investigated:** 12
- **Ticketing Platform:** ServiceNow
- **Framework:** MITRE ATT&CK
- **Focus:** Alert triage, investigation, incident management, escalation, and detection tuning

## Triage Methodology

Each alert was investigated using a consistent evidence-based triage process:

1. **Understand the alert** — Determine what the detection rule is actually identifying.
2. **Form hypotheses** — Consider both malicious and legitimate explanations.
3. **Check context** — Review change records, maintenance windows, scheduled activity, helpdesk history, known scanners, and previous incidents where available.
4. **Validate evidence** — Pivot into the available security telemetry and establish a baseline for the affected user, host, IP, or activity.
5. **Determine verdict** — Assign one of five outcomes: True Positive, False Positive, Duplicate, Escalate, or Insufficient Data.
6. **Assess severity** — Determine severity based on impact and confidence rather than relying solely on the reported alert severity.
7. **Document the decision** — Record the evidence, reasoning, severity, and response action in ServiceNow.

## Alert Summary

| Alert ID | Category | Verdict | Final Severity |
|---|---|---|---|
| CLD-0101 | Authentication | False Positive | Informational |
| CLD-0102 | Endpoint / Malware | True Positive | Sev2 |
| CLD-0103 | Network Scanning | False Positive | Informational |
| CLD-0104 | MFA / Identity | False Positive | Informational |
| CLD-0105 | Email Security | False Positive | Informational |
| CLD-0106 | Endpoint / Malware | Duplicate | N/A |
| CLD-0107 | SharePoint / File Activity | False Positive | Informational |
| CLD-0108 | Identity / Authentication | True Positive | Sev2 |
| CLD-0109 | Network / Perimeter | Escalate | Sev2 |
| CLD-0110 | Identity / Authentication | True Positive | Low |
| CLD-0111 | Email Security | Insufficient Data | Medium / On Hold |
| CLD-0112 | Identity / Authentication | False Positive | Informational |

### Shift Outcome

- **2 confirmed True Positives**
- **1 multi-site anomaly escalated according to SOP**
- **7 False Positives with documented root-cause justifications**
- **1 Duplicate identified and cross-referenced**
- **1 alert placed on hold pending additional evidence**
- **12/12 alerts investigated and dispositioned**

## ServiceNow

ServiceNow was used to simulate the operational workflow of a SOC analyst, including alert documentation, investigation work notes, severity assessment, response actions, escalation, and closure.

The completed triage worksheets and ServiceNow investigation records provide the supporting documentation for the alert decisions.

## Key Investigations

Two investigations that demonstrate the triage approach particularly well were:

- **CLD-0108 — True Positive:** An unfamiliar successful sign-in was investigated against the user's normal device, location, authentication protocol, and activity baseline, leading to a probable account-compromise determination.
- **CLD-0107 — Subtle False Positive:** A mass SharePoint deletion alert involving 1,240 files was investigated against the initiating process, scheduled HR retention activity, affected folder, and retention policy before being determined to be legitimate automation.

## Detection Tuning

The investigations also identified opportunities to reduce recurring false positives while maintaining detection coverage.

Examples included tuning mass-file-deletion detection around authorized HR retention automation and improving impossible-travel detection by distinguishing interactive authentication from non-interactive token refresh activity.

## Repository Contents

- `Cloudora_Triage_Shift.pdf` — Completed triage worksheets and shift documentation
- `cloudora_alert_queue.xlsx` — Alert queue used for the investigation

## Disclaimer

Cloudora is a fictional organization used for cybersecurity training.

This repository represents a **simulated SOC client engagement** and does not represent employment or professional work performed for Cloudora.
