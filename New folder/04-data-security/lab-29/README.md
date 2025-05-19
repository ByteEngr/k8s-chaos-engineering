## Lab 29 – Data: Database Query and Access Patterns

### Scenario
Database activity monitoring raised an alert: an application service account executed **many SELECT queries** against customer tables from a new application server IP. Your task is to decide if this is **deployment testing**, **application bug**, or **unauthorised access**.

### Investigation Objectives
- Characterise **query volume**, **tables touched**, and **time distribution**.
- Map the **server IP** to an approved app tier and change window.
- Identify **anomalies** (off-hours, new client IP, unusual query shape if logged).
- Recommend **lockdown** steps for the service account.

### Logs/Artifacts Description
You have access to:

- **DAM / database audit logs**:
  - Account, source IP, query type, object names, timestamps.
- **CMDB or inventory**:
  - Expected app servers for the service account.
- **Change tickets** (optional) for releases.

### Tasks
1. **Validate source**
   - Is the IP an expected app node?
2. **Baseline**
   - Compare to prior weeks for the same account.
3. **Scope of data**
   - High-sensitivity tables vs reference data.
4. **Hypotheses**
   - Buggy loop, ETL job, or stolen credential use.
5. **Containment**
   - Rotate creds, restrict source IPs, enable MFA on admin paths.

### Questions
- What is the fastest safe way to stop exfil via SELECT if suspected?
- How do you coordinate with developers without stopping production illegally?
- What logging would you add if object-level detail is missing?

### Indicators of Compromise
Capture:

- Service account name, source IPs, database objects, time window.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Interpret database access anomalies in application context.
