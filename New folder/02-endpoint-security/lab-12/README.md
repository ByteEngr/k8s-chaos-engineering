## Lab 12 – Endpoint: PUA and Unwanted Software Triage

### Scenario
EDR has flagged multiple detections classified as Potentially Unwanted Applications (PUA) on a developer workstation. Your task is to **triage** these: distinguish between legitimate tools (for example debuggers, remote-access software used for work) and truly unwanted or risky software, and recommend which to remove or allow via policy.

### Investigation Objectives
- Classify each detection as **approved business use**, **needs approval**, or **remove**.
- Identify **policy gaps** (for example remote access without IT-managed controls).
- Recommend **EDR policy** changes (allowlist, block, alert-only).
- Document **risk acceptance** where software must remain.

### Logs/Artifacts Description
You have access to:

- **EDR detections list**:
  - Software name, vendor, path, signature, PUA category.
- **Software inventory** (optional):
  - Installed programs and versions.
- **User and role context**:
  - Job role, team, and whether they requested admin tools.

### Tasks
1. **Group detections**
   - By category (remote access, miners, torrent, adware, dev tools).
2. **Validate business need**
   - Map each to a ticket, standard build, or exception process.
3. **Assess risk**
   - Consider data exfiltration, lateral movement, or compliance impact.
4. **Decide disposition**
   - Remove, quarantine, or allow with monitoring.
5. **Policy recommendation**
   - Draft a one-paragraph rule for the security team.

### Questions
- When is “developer convenience” an unacceptable risk?
- What is your process for time-bound exceptions?
- How would you detect misuse of an approved remote-access tool?

### Indicators of Compromise
For items you remove, capture:

- File paths, hashes, and uninstall registry keys if relevant.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Make consistent PUA decisions grounded in policy and risk.
- Communicate trade-offs to engineering and IT.
