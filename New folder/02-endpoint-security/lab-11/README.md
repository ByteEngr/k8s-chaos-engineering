## Lab 11 – Endpoint: Persistence Mechanism Hunting

### Scenario
A previously infected host was cleaned, but monitoring suggests possible re-infection or a missed persistence mechanism. Your task is to **hunt for persistence**: scheduled tasks, registry Run keys, services, and startup items that could allow the threat to survive reboot or re-establish access.

### Investigation Objectives
- Enumerate **persistence locations** relevant to the OS (Windows examples: Run keys, services, tasks, WMI).
- Correlate persistence artefacts with **timelines** around the original infection.
- Determine whether persistence is **still active** or orphaned.
- Recommend **remediation** (remove, re-image, or isolate) with evidence.

### Logs/Artifacts Description
You have access to:

- **EDR inventory / configuration** snapshots:
  - Scheduled tasks, startup items, services, autorun entries.
- **Telemetry timeline**:
  - Process creation, file writes, registry or plist changes in the persistence window.
- **Optional**: baseline comparison (“golden image”) for the same build.

### Tasks
1. **Export persistence inventory**
   - List all autorun-style entries with last-modified time if available.
2. **Highlight anomalies**
   - Unsigned binaries, unusual paths, entries created after infection time.
3. **Tie to identity**
   - Note which user context created the persistence (if logged).
4. **Validate necessity**
   - Check if any entry maps to known IT software.
5. **Plan removal**
   - Order of operations to avoid breaking the system.

### Questions
- Which persistence technique would you escalate to forensics immediately?
- How do you tell a legitimate IT tool from malware in a startup path?
- What would you re-check after removal to prove persistence is gone?

### Indicators of Compromise
Record:

- Paths, service names, task names, registry keys, or launch agent labels.
- File hashes for any binaries launched by persistence.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Navigate a structured persistence hunt without relying on a single alert.
- Explain removal risk and verification steps.
