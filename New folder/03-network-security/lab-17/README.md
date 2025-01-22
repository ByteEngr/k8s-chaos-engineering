## Lab 17 – Network: Suspicious Perimeter Traffic (Basic)

### Scenario
You are monitoring a perimeter firewall and IDS/IPS protecting a small enterprise. Overnight, the IDS generated several alerts for repeated connection attempts from an external IP range targeting SSH and RDP on your internet‑facing servers. The firewall logs also show a spike in denied connections. You must determine whether this activity is benign scanning, targeted brute force, or part of a coordinated campaign.

### Investigation Objectives
- Characterise the **source** and **pattern** of suspicious inbound traffic.
- Distinguish between generic scanning and more focused attack activity.
- Identify which internal systems were targeted and whether any access was granted.
- Recommend proactive controls (rules or signatures) to reduce risk.

### Logs/Artifacts Description
You have access to:

- **Firewall logs**:
  - Denied/allowed connection attempts, including source/destination IP, ports, action, and timestamps.
- **IDS/IPS alerts**:
  - Signatures fired (for example, SSH brute force, RDP scan).
  - Severity levels and associated metadata.
- **Optional server logs** (if available):
  - SSH/RDP authentication logs showing successful/failed logins.

These may be viewed in your SIEM or exported as raw log files.

### Tasks
1. **Summarise inbound activity**
   - Identify the main external source IPs and ranges involved.
   - Count the number of connection attempts and note targeted ports.
2. **Correlate firewall and IDS/IPS data**
   - Map firewall blocks/permits to IDS alerts to see which attempts were detected at each layer.
   - Identify any traffic that reached internal hosts.
3. **Check for successful access**
   - If server logs are available, search for:
     - Repeated failed logins from the same IPs.
     - Any successful logins that occur after a burst of failures.
4. **Assess the threat**
   - Determine whether the pattern looks like:
     - Opportunistic internet scanning.
     - Focused brute‑force attack on specific services.
     - Part of a larger coordinated campaign (for example, shared infrastructure seen in other alerts).
5. **Propose controls**
   - Suggest specific firewall, IDS, or logging changes based on your findings (for example, geo‑blocking, rate limiting, stricter logging).

### Questions
- Which external IPs are responsible for the majority of suspicious traffic?
- Which internal services and hosts are being targeted, and on which ports?
- Did any inbound connections move from blocked to allowed states over time?
- What evidence supports your classification of the activity (scan vs attack)?
- What concrete network‑level changes would you implement to mitigate this risk?

### Indicators of Compromise
Document:

- Suspicious source IPs and their associated behaviours.
- Targeted ports/services (for example, TCP/22, TCP/3389).
- Any notable patterns (for example, timing, geographic origin, or signature names).

These IOCs can later be used for:

- Blocking on perimeter devices.
- Additional correlation rules in the SIEM.

### Expected Analyst Outcome
By the end of this lab, a junior network security analyst should be able to:

- Interpret and correlate firewall and IDS/IPS logs for basic perimeter threats.
- Identify likely brute‑force or scanning behaviour and distinguish it from noise.
- Extract network‑level IOCs and propose concrete defensive actions.

