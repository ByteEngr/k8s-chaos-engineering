## Lab 09 – Endpoint: Malware Execution on User Workstation (Basic)

### Scenario
You are supporting a corporate SOC that uses an Endpoint Detection and Response (EDR) platform across all Windows workstations. A user has reported that their system “froze briefly” after opening an unexpected email attachment. Shortly afterwards, the EDR generated a **malware detection alert** for a suspicious executable launched from the user’s Downloads folder. You must investigate the alert and determine the scope of impact.

### Investigation Objectives
- Confirm whether a malicious file executed on the endpoint.
- Identify the **process tree** associated with the suspicious executable.
- Determine whether the malware established **persistence** or **network connections**.
- Decide whether the host should be isolated and escalated for remediation.

### Logs/Artifacts Description
For this lab, you have access to:

- **EDR alert details**:
  - Detection name, severity, file path, hash, and detection timestamp.
  - User context under which the file executed.
- **Endpoint process/telemetry logs**:
  - Process creation events (parent/child relationship, command line).
  - Module loads or script engine usage (if available).
- **Network connection events (from the endpoint agent)**:
  - Outbound connections initiated by the suspicious process.
  - Destination IPs, ports, and basic metadata.

Artifacts may be reviewed directly in the EDR console or exported as JSON/CSV.

### Tasks
1. **Review the EDR alert**
   - Capture the file name, path, hash, and user associated with the detection.
   - Note the detection rule or signature name for context.
2. **Reconstruct the process tree**
   - Identify the parent process (for example, email client or browser).
   - Identify any child processes spawned by the suspicious binary.
   - Review command‑line arguments for evidence of script execution or LOLBins.
3. **Examine network activity**
   - Filter network events to those initiated by the suspicious process.
   - Identify destinations, ports, and whether connections were successful.
4. **Assess persistence attempts**
   - Look for events that suggest persistence (for example, registry run keys, scheduled tasks, startup folders) if your telemetry includes them.
5. **Decide on response**
   - Based on gathered evidence, decide whether to:
     - Quarantine or isolate the host.
     - Trigger malware eradication procedures.
     - Escalate to a deeper forensic review.

### Questions
- What was the **initial vector** that led to the malware execution?
- Which **processes** directly or indirectly executed the suspicious file?
- Did the file attempt to reach out to external infrastructure? If so, how?
- Is there evidence that the malware attempted or achieved persistence?
- What immediate response actions would you recommend to the incident handler?

### Indicators of Compromise
Identify and record:

- File name, path, and hash of the suspicious executable.
- Any suspicious domains or IPs contacted by the process.
- Notable process names or command lines that might be detected across other endpoints.

Classify IOCs as:

- **File‑based IOCs** (hashes, paths).
- **Network IOCs** (IPs, domains, ports).
- **Behavioural IOCs** (unusual parent/child process relationships).

### Expected Analyst Outcome
By the end of this lab, a junior endpoint security analyst should be able to:

- Interpret an EDR malware detection alert in context.
- Rebuild a basic process tree and identify suspicious behaviours.
- Extract endpoint‑level IOCs suitable for detection content or further hunting.
- Recommend appropriate containment and remediation steps for the impacted host.

