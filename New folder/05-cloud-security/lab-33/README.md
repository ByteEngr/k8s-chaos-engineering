## Lab 33 – Cloud: Unusual API and Cross-Region Activity

### Scenario
Cloud monitoring shows a spike in **API calls** from a workload identity in **Region A**, while the application is supposed to run only in **Region B**. You must determine if this is **misconfiguration**, **failover testing**, or **token misuse**.

### Investigation Objectives
- Profile **which APIs** were called and with what outcomes (success vs denied).
- Map the identity to **expected regions** and **deployment artifacts**.
- Identify **credential sources** (access keys, instance roles, federation).
- Recommend **containment** (revoke keys, restrict regions, fix trust policy).

### Logs/Artifacts Description
You have access to:

- **API management / CloudTrail data events** (conceptual):
  - Service name, action, region, identity, error codes, volume.
- **Infrastructure-as-code repo metadata** (optional): intended regions.
- **Cost anomaly** hints (optional): unexpected regional usage.

### Tasks
1. **Cluster API actions**
   - Read vs write; data plane vs control plane.
2. **Validate identity**
   - Is the caller a human user, role, or workload role?
3. **Region justification**
   - DR, CDN misrouting, or attacker exploration.
4. **Containment**
   - Disable keys, update trust policies, enforce SCP guardrails (conceptual).
5. **Hunt**
   - Search for the same identity in other accounts.

### Questions
- Which API errors suggest enumeration vs normal app retries?
- How do you verify the identity is not stolen (session issuer, MFA, IP)?
- What SCP patterns reduce region sprawl?

### Indicators of Compromise
Record:

- Identity ARN, access key IDs (last 4), regions, top API actions, error patterns.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate cross-region API anomalies with identity-centric reasoning.
