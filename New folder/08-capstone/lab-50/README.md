## Lab 50 – Capstone: Cloud-Initiated Hybrid Kill Chain (Advanced)

### Scenario
You are the incident lead for a second multi-stage case: this time the initial vector appears to be a compromised cloud account that was used to access on-premises resources via a hybrid connection. Your task is to **reconstruct the full kill chain** across cloud and on-prem, document IOCs and containment actions, and present a concise after-action summary.

### Investigation Objectives
- Correlate events from **email**, **endpoint**, **network**, and **cloud** telemetry into a single case.
- Identify the **kill chain**: initial access, execution, persistence, lateral movement, data access, and potential exfiltration.
- Produce a concise but complete **incident narrative** with key IOCs and recommended response actions.

### Logs/Artifacts Description
You have access to:

- **Email security logs**:
  - Phishing messages, senders, recipients, URLs, and attachment names.
- **VPN and identity logs**:
  - Unusual logins by privileged accounts from new locations.
- **Endpoint telemetry**:
  - Malware or tool detections on specific workstations and servers.
- **Network and proxy logs**:
  - Outbound traffic to suspicious domains and IPs.
- **Cloud audit logs**:
  - Console logins, IAM changes, and data access events for storage services.

Assume these artifacts cover at least a one‑week window.

### Tasks
1. **Build a timeline**
   - Place key events (phishing, logins, endpoint alerts, cloud activity) on a common timeline.
   - Identify the earliest suspicious event.
2. **Propose a kill chain**
   - For each phase (initial access, execution, persistence, lateral movement, data access/exfiltration), identify:
     - Which events and logs support that phase.
     - Which assets and identities are involved.
3. **Cluster IOCs**
   - Build a consolidated IOC list across:
     - Email (senders, URLs, attachment names).
     - Endpoint (file hashes, processes, paths).
     - Network (IPs, domains, ports).
     - Cloud (accounts, roles, storage objects).
4. **Assess impact**
   - Determine which systems and data sets are likely impacted.
   - Evaluate whether data exfiltration is probable, possible, or unlikely based on access and network logs.
5. **Define response plan**
   - Recommend:
     - Immediate containment actions (account lockouts, key revocation, host isolation).
     - Short‑term remediation (log review, IOC sweeps, password resets).
     - Medium‑term improvements (new detections, playbooks, and controls).

### Questions
- What is your proposed **sequence of events** from the first phishing email to the final data access alert?
- Which identities (user accounts, service accounts, cloud roles) were compromised or abused?
- Which systems and data stores are most at risk based on the evidence?
- What evidence do you have for or against actual data exfiltration?
- If you had one hour with leadership, how would you summarise this incident and your recommended actions?

### Indicators of Compromise
Produce a capstone IOC package including:

- Email IOCs – senders, subjects, attachment names, and URLs.
- Endpoint IOCs – malicious file hashes, process names, persistence artefacts.
- Network IOCs – IPs, domains, and key ports used in C2 or exfiltration.
- Cloud IOCs – suspicious accounts, roles, and resource identifiers.

Flag which IOCs are **campaign‑level** and should be deployed broadly as detections.

### Expected Analyst Outcome
By the end of this capstone lab, a junior analyst who has completed the previous labs should be able to:

- Correlate telemetry across multiple domains (SOC, endpoint, network, data, cloud).
- Build a coherent, evidence‑based incident narrative.
- Present a clear, prioritised response and remediation plan suitable for both technical and non‑technical stakeholders.

