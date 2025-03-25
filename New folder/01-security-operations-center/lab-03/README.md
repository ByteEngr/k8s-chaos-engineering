## Lab 03 – SOC: Escalation Decision Under Time Pressure

### Scenario
A high-severity alert has just fired for potential data exfiltration from a file server. The duty lead is in a meeting and has asked you to **triage and decide** within 15 minutes whether to escalate to Tier-2 and incident response, or to close as a false positive. You must document your reasoning clearly.

### Investigation Objectives
- Determine whether the alert matches a **known admin job** (backup, migration) or **unexpected behaviour**.
- Quantify **data volume and direction** (inbound vs outbound, internal vs external).
- Identify the **user or service account** driving the activity.
- Make a **binary recommendation**: escalate now, hold for monitoring, or close with rationale.

### Logs/Artifacts Description
You have access to:

- **SIEM alert**:
  - Rule: “Large outbound transfer from file server” with bytes transferred, duration, and destination.
- **File share / NAS audit logs**:
  - Open/read/write counts by user, paths accessed, and timestamps.
- **Proxy or firewall flow metadata**:
  - Top destinations and ports from the file server’s IP (even if encrypted).

### Tasks
1. **Confirm scope**
   - Identify the server, share or path involved, and the time window.
2. **Validate identity**
   - Tie the activity to a user or service account and check if it is privileged.
3. **Check for change correlation**
   - See if a change ticket or maintenance window explains the volume.
4. **Assess risk**
   - Decide if destination, protocol, or path suggests exfiltration vs legitimate sync.
5. **Record the decision**
   - Write a 5-line escalation note: finding, risk, action, owner, next check.

### Questions
- What volume and destination would make you escalate even without content inspection?
- What benign explanations are you ruling out, and how?
- What single additional log would most reduce uncertainty?

### Indicators of Compromise
Capture:

- Destination IPs, domains, or cloud endpoints involved in large transfers.
- User or service account identifiers tied to the activity.
- Unusual paths or share names if present in audit logs.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Make a time-boxed triage decision with explicit assumptions.
- Differentiate bulk legitimate transfers from suspicious exfil patterns at a metadata level.
- Escalate or close with defensible documentation.
