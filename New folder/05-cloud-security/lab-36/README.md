## Lab 36 – Cloud: Cloud Security Week Recap

### Scenario
You are summarising cloud investigations from the week: console anomalies, IAM drift, API spikes, and credential issues. Produce **three priorities** for the cloud security roadmap and **metrics** to track progress.

### Investigation Objectives
- Prioritise risks discovered across labs (identity, logging, data, governance).
- Propose **quick wins** vs **strategic projects**.
- Define **KPIs** (for example MFA coverage, key age, policy deny rates).
- Draft a **stakeholder summary** for engineering leadership.

### Logs/Artifacts Description
You have access to:

- **Synthetic weekly stats** in your workbook (counts of alerts by category).

### Tasks
1. **Theme the week**
   - Identity vs data vs API abuse.
2. **Pick three initiatives**
   - Example: OIDC for CI, org-level guardrails, central log archive.
3. **Owners and milestones**
   - Who does what by when.
4. **Metrics**
   - Baseline now vs target next quarter.
5. **Risks**
   - What happens if nothing changes.

### Questions
- Which control reduces incident likelihood the most per effort?
- How do you win engineering buy-in?
- What would you *not* centralise in security?

### Indicators of Compromise
Provide a **generic cloud hunt pack** idea list:

- New external owners on storage, sudden IAM admins, denied API storms.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Translate tactical cloud findings into a programme-level narrative.
