## Lab 27 – Data: Personal Cloud Storage Uploads

### Scenario
Proxy and DLP metadata show large uploads to a **personal cloud storage** domain from a finance workstation during off hours. Your task is to determine whether this is **personal use**, **shadow IT**, or **data exfiltration**, using metadata only.

### Investigation Objectives
- Quantify **volume and timing** vs the user’s baseline.
- Identify the **application or browser** responsible if visible.
- Check for **MFA or corporate SSO** vs personal account indicators.
- Recommend **technical and policy** next steps.

### Logs/Artifacts Description
You have access to:

- **Proxy logs** with host, bytes, user, URL paths (partial), category.
- **DLP alerts** referencing the same timeframe.
- **Endpoint process logs** (optional): process name initiating HTTPS.

### Tasks
1. **Baseline comparison**
   - Same user’s history for similar destinations.
2. **Account type inference**
   - URL patterns suggesting personal vs corporate tenant if present.
3. **Sensitivity**
   - What data classes the user routinely handles.
4. **Decision**
   - Coaching, block category, or IR escalation.
5. **Controls**
   - CASB, SSO enforcement, device compliance checks.

### Questions
- What metadata suggests personal cloud vs sanctioned SaaS?
- When would you treat this as insider risk immediately?
- What user interview questions stay fair and factual?

### Indicators of Compromise
Capture:

- Domains, approximate volumes, user and host identifiers.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Reason about cloud uploads without full decryption visibility.
