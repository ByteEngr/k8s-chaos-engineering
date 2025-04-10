## Lab 25 – Data: Suspected Data Exfiltration over HTTPS (Intermediate)

### Scenario
You are an analyst in a SOC supporting a technology company that hosts sensitive customer data. DLP alerts and proxy logs indicate unusually large HTTPS uploads from a single engineering workstation to a file‑sharing site not on the approved list. There is concern that sensitive source code or customer data may have been exfiltrated.

### Investigation Objectives
- Confirm whether a significant volume of data was transferred from the workstation.
- Identify the **destination domains/URLs** and associated user accounts, if possible.
- Determine whether the data transfer aligns with legitimate business activity.
- Recommend containment and follow‑up actions if exfiltration is suspected.

### Logs/Artifacts Description
You have access to:

- **DLP or proxy alerts**:
  - Rule name, severity, source IP/user, destination domain/URL, volume, and timestamps.
- **Web proxy logs**:
  - HTTP(S) request logs including host, URI, method, bytes sent/received, and user ID.
- **Endpoint logs** (if available):
  - Process responsible for initiating the connections (for example, browser, sync agent).

Assume packets are encrypted (no content inspection) but metadata is rich.

### Tasks
1. **Review DLP/proxy alerts**
   - Identify the user, workstation, and time window associated with the alerts.
   - Note the volume of data transferred and any repeated patterns.
2. **Analyse proxy metadata**
   - Filter proxy logs for the source workstation over the relevant time window.
   - Group by destination domain and URI to identify:
     - Non‑approved file‑sharing or storage sites.
     - Specific upload or API endpoints.
3. **Correlate with user context**
   - Determine the user’s role and whether they are expected to handle sensitive data.
   - Check for any recent tickets or projects that might justify large transfers.
4. **Assess exfiltration likelihood**
   - Based on destination, timing, and user role, judge whether the activity is:
     - Clearly malicious,
     - Suspicious and unjustified, or
     - Legitimate but poorly documented.
5. **Define next steps**
   - Recommend technical and procedural actions (for example, temporary account suspension, endpoint imaging, user interview, policy update).

### Questions
- How much data (in bytes/MB/GB) appears to have been uploaded from the workstation?
- Which domains and specific URLs were involved in the large transfers?
- Does the timing or volume of activity stand out compared to the user’s normal behaviour?
- What additional data or approvals would you seek before concluding exfiltration has occurred?
- What immediate controls would you propose to prevent further potential data loss?

### Indicators of Compromise
Capture:

- Destination domains and specific upload URLs of concern.
- Source workstation and user account identifiers.
- Any associated application user‑agents or processes that could be used for further detection.

Classify indicators as:

- **Suspected exfiltration channels** (domains/URLs).
- **Potential insider threat identifiers** (user, host).

### Expected Analyst Outcome
By the end of this lab, a junior data security analyst should be able to:

- Use DLP/proxy telemetry to characterise potential data exfiltration.
- Distinguish between normal large data transfers and suspicious uploads.
- Document key IOCs and propose next steps for containment and investigation.

