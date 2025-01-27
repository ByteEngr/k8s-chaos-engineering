## Lab 18 – Network: Internal Lateral Movement and Segmentation

### Scenario
Internal sensors have detected unusual traffic between two VLANs that should be segmented. Your task is to **analyse** the flow: identify source and destination hosts, protocol and port, and whether this suggests lateral movement, data staging, or a misconfiguration. Recommend whether to block and escalate.

### Investigation Objectives
- Reconstruct **allowed vs denied** flows using firewall or east-west telemetry.
- Determine whether traffic matches **expected admin paths** (jump boxes, backups).
- Identify **accounts or services** involved if authentication metadata exists.
- Propose **segmentation fixes** (rule, zone, or micro-segment policy).

### Logs/Artifacts Description
You have access to:

- **East-west firewall or NGFW logs**:
  - Source/destination IP, zones, ports, action, bytes, timestamps.
- **Netflow or flow logs** (optional):
  - Conversation pairs and duration.
- **Internal DNS or DHCP** (optional):
  - Hostname resolution for internal IPs.

### Tasks
1. **Label endpoints**
   - Resolve IPs to roles (server, workstation, printer, IoT) using inventory tags.
2. **Characterise the session**
   - Single burst vs long-lived session; symmetric vs asymmetric bytes.
3. **Rule check**
   - Identify which rule permitted or denied the traffic.
4. **Threat vs misconfig**
   - Decide if behaviour fits admin work, misrouted traffic, or suspicious pivoting.
5. **Recommendations**
   - Block, monitor, or change architecture; include monitoring use cases.

### Questions
- What evidence would prove lateral movement vs a wrong default gateway?
- When would you involve the server owner before blocking?
- What detection would you add after a confirmed misconfiguration?

### Indicators of Compromise
Capture:

- Internal IP pairs, ports, protocols, and any named services.
- User or machine accounts if shown in proxy or auth logs.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Interpret east-west logs in segmentation investigations.
- Recommend controls that reduce blast radius without breaking business flows.
