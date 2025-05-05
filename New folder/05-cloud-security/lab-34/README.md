## Lab 34 – Cloud: Credential and Service Key Abuse

### Scenario
A set of **long-lived access keys** for an automation account was found in a public code snippet (simulated). Cloud logs show recent use from **unexpected IP ranges** and calls to **storage and IAM APIs**. Your task is to assess abuse, revoke credentials safely, and harden automation practices.

### Investigation Objectives
- Determine **when keys were created** and **last used**.
- Identify **which APIs** were invoked and whether IAM tampering occurred.
- Map keys to **workloads** (CI runners, scripts, Lambdas).
- Design **rotation and secret management** improvements.

### Logs/Artifacts Description
You have access to:

- **Access key usage events** and **last used timestamps**.
- **API audit logs** for the automation principal.
- **Code repository scan results** (simulated): file path where key was exposed.

### Tasks
1. **Establish blast radius**
   - Accounts, buckets, and roles reachable by the key.
2. **Malicious vs legitimate use**
   - Compare IP ranges to known CI egress IPs.
3. **Revocation order**
   - Replace credentials in automation, then deactivate old keys.
4. **Verify**
   - Ensure services still work; watch for retries from old keys.
5. **Prevent recurrence**
   - Secret scanning, OIDC for CI, short-lived credentials.

### Questions
- Why are long-lived keys risky even with “read-only” policies?
- What is your rollback plan if rotation breaks production jobs?
- How would you detect key exfiltration in near real time?

### Indicators of Compromise
Capture:

- Access key ID (partial), suspicious IPs, IAM actions, buckets accessed.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Respond to exposed cloud credentials with safe revocation and hardening steps.
