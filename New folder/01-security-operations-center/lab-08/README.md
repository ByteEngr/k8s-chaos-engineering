## Lab 08 – SOC: Triage Recap and Escalation Report

### Scenario
You have completed a set of triage tasks over the week. Your task is to **summarise** your findings in a short escalation report: how many alerts you reviewed, how many you escalated vs closed, key IOCs and affected assets, and any patterns or recommendations for Tier-2 or detection tuning.

### Investigation Objectives
- Aggregate **metrics** from your reviewed tickets (counts, severities, categories).
- Highlight **recurring themes** (same rule, same business unit, same false-positive cause).
- Propose **2–3 concrete improvements** (detection, training, asset tagging).
- Produce a **stakeholder-safe summary** (no victim blaming, clear ask).

### Logs/Artifacts Description
You have access to:

- **Your closed ticket export** for the week (synthetic or anonymised):
  - Alert type, resolution, time spent, IOCs recorded.
- **Optional**: team baseline metrics (average triage time, escalation rate).

### Tasks
1. **Build a dashboard on paper**
   - Table: category, count escalated, count closed, top root cause.
2. **Pick three stories**
   - One true positive, one false positive, one “needs better data.”
3. **IOCs and assets**
   - Consolidate the most important IOCs your team should track.
4. **Recommendations**
   - Detection tuning, logging gaps, or playbook updates.
5. **Executive blurbs**
   - Five sentences an IT lead could read in under a minute.

### Questions
- Which metric best shows triage quality, not just speed?
- What would you measure next week to see if recommendations worked?
- How do you report uncertainty without sounding evasive?

### Indicators of Compromise
Attach a **weekly IOC summary**:

- Top external domains/IPs worth blocking or threat-intel submission.
- Internal hosts that appeared more than once in different alerts.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Communicate operational results clearly to technical and non-technical readers.
- Turn individual tickets into systemic improvements.
- Maintain professional tone in written reports.
