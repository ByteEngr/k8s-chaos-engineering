## Lab 47 – Threat Investigation & Response: Critical Server Incident and Playbook

### Scenario
A critical database server shows signs of compromise: unexpected local admin logons, new scheduled tasks, and outbound connections to rare IPs. Operations needs a **controlled response** to avoid downtime. Your task is to follow a **playbook mindset**: preserve evidence, contain, and coordinate recovery.

### Investigation Objectives
- Establish **severity** based on data sensitivity and service criticality.
- Identify **persistence** and **credential exposure** risks.
- Define **containment** that balances uptime vs risk (snapshots, network isolation).
- Produce a **playbook checklist** for future similar servers.

### Logs/Artifacts Description
You have access to:

- **Windows security events** / OS audit logs (conceptual).
- **EDR timeline** on the server.
- **Firewall flows** from the server IP.
- **Backup and snapshot availability** notes (simulated).

### Tasks
1. **Triage checklist**
   - What to capture before isolation (if safe).
2. **Evidence preservation**
   - Memory/image decisions at a high level.
3. **Containment**
   - Network segmentation, admin password rotations, service account review.
4. **Recovery**
   - Rebuild vs restore from known-good backup; verification steps.
5. **Post-incident**
   - Patch priorities, monitoring additions, access reviews.

### Questions
- When is snapshot-first the wrong move?
- What server roles require extra legal care (PCI/health data)?
- How do you coordinate with DBAs without blame culture?

### Indicators of Compromise
Record:

- Accounts, tasks, binaries, IPs, and any unusual listening ports.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Run a structured critical-server response with clear operational trade-offs.
