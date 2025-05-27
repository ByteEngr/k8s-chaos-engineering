## Lab 43 – Threat Investigation & Response: Ransomware in a Branch Office (Advanced)

### Scenario
You are the on‑call incident responder for a managed SOC. A branch office reports that multiple file servers suddenly have encrypted files with a new extension and ransom notes in each directory. Endpoint alerts show suspicious lateral movement in the hours leading up to the encryption event. Your task is to **investigate and coordinate response** to this suspected ransomware incident.

### Investigation Objectives
- Identify **patient zero** and the initial infection vector.
- Map the **lateral movement path** and identify all compromised systems.
- Determine the **time window** of encryption and whether data exfiltration occurred.
- Recommend immediate and follow‑up response actions.

### Logs/Artifacts Description
You have access to:

- **Endpoint telemetry**:
  - Process creation, logon events, and suspicious tool usage (for example, PSExec, PowerShell).
- **Windows event logs or equivalent**:
  - Authentication events across key servers and workstations.
- **Network logs**:
  - Connections between endpoints, especially SMB/RDP.
- **File server logs** (if available):
  - File rename/write operations and user accounts performing them.

All data is time‑bounded to the 24 hours leading up to and including the encryption event.

### Tasks
1. **Confirm encryption event**
   - Identify which servers were affected and when encryption began.
   - Note the presence and content of ransom notes (conceptually; no need to reproduce text).
2. **Identify patient zero**
   - Examine endpoint alerts and logon events to find the first host exhibiting suspicious behaviour.
   - Correlate that host’s activity with initial signs of encryption or lateral movement.
3. **Trace lateral movement**
   - Use authentication and process execution logs to map:
     - Which accounts moved between which systems.
     - Where administrative tools (for example, PSExec) were used.
4. **Assess potential data theft**
   - Look for outbound connections to unusual external IPs or domains in the hours prior to encryption.
   - Note any large data transfers that might indicate exfiltration.
5. **Recommend response actions**
   - Propose immediate containment steps (isolation, password resets, key revocation).
   - Outline short‑term and medium‑term remediation actions.

### Questions
- Which host is most likely patient zero, and what evidence supports that conclusion?
- Which user accounts were abused for lateral movement, and on which systems?
- Did encryption occur simultaneously across systems or in a staged pattern?
- Is there evidence suggesting data was exfiltrated before encryption?
- What are your top three response priorities for the next 60 minutes?

### Indicators of Compromise
Document:

- Hostnames/IPs of impacted systems.
- Suspicious tools and processes used (for example, specific command lines).
- Accounts associated with lateral movement and file modifications.
- Any external IPs/domains contacted around the time of the incident.

Separate IOCs into:

- **Initial access IOCs** – phishing, exploits, or initial malware beacons.
- **Lateral movement IOCs** – tools, credentials, and protocols.
- **Impact IOCs** – file extensions, ransom note paths, and encryption‑related processes.

### Expected Analyst Outcome
By the end of this lab, a junior incident responder should be able to:

- Reconstruct a basic attack timeline for a ransomware incident.
- Identify key systems and accounts involved in initial access and spread.
- Propose concrete, prioritised response actions suitable for coordination with IT and management.

