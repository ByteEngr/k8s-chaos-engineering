## Lab 16 – Endpoint: Endpoint Recap and Multi-Source Correlation

### Scenario
You are wrapping up the endpoint section of the course. You have **one synthetic bundle**: an EDR alert plus a matching proxy log line and a suspicious login. Your task is to **tell one coherent story** across sources and list what you would still ask for in real life.

### Investigation Objectives
- Align **timestamps** across EDR, identity, and network logs.
- Identify **one primary hypothesis** (infection, credential theft, or policy violation).
- List **gaps** in logging that would block a full conclusion.
- Propose **two improvements** to visibility or process.

### Logs/Artifacts Description
You have access to:

- **EDR**: process and file alert with hash.
- **Proxy**: URL category and user ID.
- **IdP/VPN**: login from unusual location near the same time.

### Tasks
1. **Build a timeline**
   - Order events in UTC with sources cited.
2. **Correlate**
   - Show how the three artefacts support the same narrative.
3. **Hypothesis and alternatives**
   - State the leading explanation and one benign alternative.
4. **Improvements**
   - Logging, asset tagging, or playbook updates.
5. **Executive summary**
   - 6 sentences maximum.

### Questions
- Which log source is your “source of truth” for time?
- What would change your mind about the hypothesis?
- What would you automate next time to speed this up?

### Indicators of Compromise
Produce a **mini IOC package** that links all sources:

- Hash, URL, domain, user, and host identifiers.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Integrate endpoint telemetry with adjacent security data.
- Communicate limitations honestly.
