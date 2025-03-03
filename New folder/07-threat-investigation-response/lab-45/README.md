## Lab 45 – Threat Investigation & Response: Insider Threat Timeline

### Scenario
HR and legal escalated concerns about **after-hours access** to sensitive file shares by a privileged user. Your task is to build a **timeline** of access events, determine scope of data touched, and recommend **technical and HR-aligned** next steps.

### Investigation Objectives
- Correlate **authentication**, **file access**, and **DLP** events for the user.
- Identify **anomalies** vs plausible job duties (projects, on-call).
- Scope **data assets** potentially affected.
- Recommend **preserve-and-hold** steps without tipping off unduly (policy-dependent).

### Logs/Artifacts Description
You have access to:

- **VPN/SSO sign-in logs** with device and location metadata.
- **File share audit logs** (SMB) or collaboration audit logs.
- **DLP events** involving the same user.
- **Optional**: badge access or HR schedule notes (simulated).

### Tasks
1. **Build a 14-day timeline**
   - Highlight off-hours clusters.
2. **Validate business context**
   - Tickets, managers, project codes (simulated prompts).
3. **Data scope**
   - Sensitive folders accessed and approximate volume if available.
4. **Risk decision**
   - Escalate to formal insider programme vs benign explanation.
5. **Technical controls**
   - Temporary removal of excessive rights, enhanced logging, MFA re-check.

### Questions
- What evidence would you need before recommending account suspension?
- How do you balance employee privacy with investigation needs?
- What mistakes commonly destroy trust with HR/legal?

### Indicators of Compromise
Document factual indicators (not conclusions):

- File paths, share names, session IDs, source IPs, devices.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Conduct insider-adjacent investigations with careful, policy-aware documentation.
