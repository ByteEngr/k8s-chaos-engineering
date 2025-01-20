## Lab 40 – Threat Analysis: Malware Family Profile

### Scenario
Multiple endpoints triggered alerts with similar file names, paths, and network destinations. Your task is to build a **malware family profile** (behaviour, persistence, network) suitable for detection engineering and hunting.

### Investigation Objectives
- Summarise **common behaviours** across detections (TTPs in plain language).
- Identify **stable IOCs** vs **volatile IOCs**.
- Map to **MITRE-style tactics** at a high level (without theory lecture).
- Propose **detection ideas** (log sources + logic concept).

### Logs/Artifacts Description
You have access to:

- **EDR detection exports**:
  - Hashes, paths, command lines, parent processes.
- **Network indicators**:
  - C2 domains/IPs and beaconing patterns.

### Tasks
1. **Group samples**
   - Cluster by hash similarity or shared C2.
2. **Describe behaviour**
   - Persistence, credential access, lateral movement attempts.
3. **Family naming**
   - Use vendor names if present; otherwise neutral internal label.
4. **IOC tiers**
   - Network IOCs for blocking; host IOCs for hunting.
5. **Coverage gaps**
   - What logging would improve confidence.

### Questions
- Which behaviours are most reliable for detection vs easily changed by attackers?
- How do you avoid over-fitting to one sample?
- What would you share with IT vs keep in SOC-only channels?

### Indicators of Compromise
Deliver:

- File hashes, paths, mutexes/registry keys (if present), C2 domains/IPs.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Convert alerts into a structured malware family brief.
