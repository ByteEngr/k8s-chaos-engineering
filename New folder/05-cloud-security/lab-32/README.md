## Lab 32 – Cloud: IAM Policy Change Review

### Scenario
An IAM policy change grants a **broad role** to a service account. Your task is to review **who made the change**, **from where**, and whether the new permissions are justified or create **excessive risk**.

### Investigation Objectives
- Identify the **principal** that modified IAM and the **change payload**.
- Compare new permissions to **least privilege** expectations for that workload.
- Determine whether the change aligns with a **change ticket** or release.
- Recommend **rollback** or **scoped replacement** policies.

### Logs/Artifacts Description
You have access to:

- **CloudTrail-style audit records**:
  - `PutRolePolicy`, `AttachRolePolicy`, `CreateUser`, and similar events.
- **Resource tags** showing environment (prod vs dev) and owner.
- **CI/CD identity roles** involved in deployments (optional).

### Tasks
1. **Extract the diff**
   - Old vs new permissions for the affected role.
2. **Validate business context**
   - Map service account to application name and data sensitivity.
3. **Risk rating**
   - Data exfiltration paths opened by new permissions.
4. **Rollback plan**
   - Exact API actions to revert or replace with tighter policy.
5. **Detection**
   - Alerts for similar changes in future.

### Questions
- When is “temporary broad access” acceptable, and how is it time-bounded?
- What proves the change came from CI/CD vs a stolen admin session?
- How do you document exceptions for auditors?

### Indicators of Compromise
Capture:

- Actor ARN, source IP, policy document identifiers, affected role name.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Review IAM changes with a structured least-privilege lens.
