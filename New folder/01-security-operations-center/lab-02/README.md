## Lab 02 – SOC: Multi-Alert Triage and Correlation

### Scenario
You are on the SOC morning shift. Overnight, several alerts have queued for the same subnet: suspicious outbound connections, a possible brute-force attempt, and an unusual after-hours login. Your task is to **correlate** these alerts, decide if they are linked or separate incidents, and prioritise which to escalate first.

### Investigation Objectives
- Decide whether the alerts describe **one incident** or **multiple unrelated issues**.
- Build a **short timeline** that orders events by time and source host.
- Identify overlaps in **user accounts**, **hosts**, or **external IPs** across alerts.
- Recommend **escalation order** with a one-line justification for each.

### Logs/Artifacts Description
For this lab, you have access to:

- **SIEM alert queue (export)**:
  - Multiple alert types with fields: rule name, severity, source IP, user, destination, time range.
- **Authentication logs**:
  - VPN or SSO logins with success/failure, source IP, and geolocation if available.
- **Perimeter or firewall denies** (optional):
  - Failed inbound attempts tied to the same external IPs seen in other alerts.

Assume CSV/JSON exports or a SIEM workbench view.

### Tasks
1. **Inventory the queue**
   - List each alert ID, type, severity, and affected host or user.
2. **Look for relationships**
   - Pivot on shared IPs, hostnames, users, or time windows (for example within 60 minutes).
3. **Separate signal from noise**
   - Mark each alert as likely **related**, **possibly related**, or **unrelated** to the main cluster.
4. **Prioritise**
   - Rank what you would investigate first if you only had 30 minutes (for example credential abuse before noisy scanning).
5. **Document handoff**
   - Write three bullet points another analyst would need to continue the case.

### Questions
- Which alerts share a common host, user, or external indicator?
- What is the earliest suspicious event in the cluster, and what does it suggest?
- If one alert is a false positive, does it change your view of the others?
- What would you ask Tier-2 to validate with endpoint or email data?

### Indicators of Compromise
Record IOCs that appear in **more than one** alert or log source, for example:

- External IPs or domains seen across alerts.
- User accounts that appear in both auth and SIEM data.
- Internal hosts that show multiple alert types.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Compare multiple queued alerts and explain possible links.
- Produce a concise correlation summary suitable for a ticket update.
- Escalate the highest-risk thread first with clear reasoning.
