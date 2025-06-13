## Lab 23 – Network: Internal Segmentation Violation

### Scenario
A compliance control requires that payment systems cannot initiate connections to developer workstations. Logs show **unexpected SMB** from a payment app server to a laptop subnet. Your task is to validate if this is **expected admin work**, **malware**, or **bad architecture**, and what to block.

### Investigation Objectives
- Prove or disprove **business justification** for the connection.
- Identify **which process or service account** initiated the traffic.
- Map the path against **intended network zones**.
- Recommend **architecture and rule changes**.

### Logs/Artifacts Description
You have access to:

- **Internal firewall logs** with zones and rules hit.
- **Server application logs** (payment app) showing scheduled jobs or integrations.
- **AD service account** usage if tied to the server.

### Tasks
1. **Timeline the sessions**
   - Frequency, duration, bytes transferred.
2. **Validate accounts**
   - Which credential was used for SMB if visible.
3. **Talk to data owners (simulated)**
   - List questions you would ask the app owner.
4. **Risk**
   - PCI-style thinking: data paths and segmentation violations.
5. **Remediation**
   - Jump host, agent-based file transfer, or API instead of SMB.

### Questions
- What log proves intent vs opportunistic scanning inside the network?
- When would you isolate the server before finishing analysis?
- How do you document a segmentation exception safely?

### Indicators of Compromise
Record:

- Internal IPs, SMB signatures, and service account names.
- Any filenames or share names if present in logs.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate segmentation violations with compliance context.
