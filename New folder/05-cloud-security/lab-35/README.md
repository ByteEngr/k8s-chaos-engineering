## Lab 35 – Cloud: Failed and Successful Login Correlation

### Scenario
Identity monitoring shows **many failed logins** to cloud consoles followed by a **successful login** without MFA from a new device profile. Your task is to determine if this is **credential stuffing**, **password spray**, or an **account takeover**, and what to do next.

### Investigation Objectives
- Quantify **failure patterns** (same IP vs distributed, same user vs many users).
- Correlate failures to the **successful session** (timing, IP, user agent).
- Check **MFA status** and **risk-based prompts**.
- Recommend **account and session** remediation.

### Logs/Artifacts Description
You have access to:

- **Sign-in logs** with success/failure reason codes.
- **Risk detections** from the cloud IdP (if enabled).
- **Optional**: corporate password reset tickets and helpdesk notes.

### Tasks
1. **Classify attack type**
   - Spray vs targeted vs user typo lockouts.
2. **Pivot to success**
   - Identify the first successful auth after failures.
3. **Post-auth activity**
   - Any sensitive actions within minutes.
4. **User verification**
   - Steps to validate with the account owner.
5. **Controls**
   - MFA enforcement, geo allowlists, leaked credential checks.

### Questions
- When do failed logins alone justify an incident?
- How do you avoid locking out the real user during response?
- What signals suggest automated tooling vs human attacker?

### Indicators of Compromise
Record:

- Source IPs, user agents, success/failure event IDs, account UPN.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Correlate authentication brute-force patterns with follow-on success.
