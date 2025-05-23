## Lab 46 – Threat Investigation & Response: Department Outbreak vs Lateral Movement

### Scenario
EDR shows detections on **multiple hosts in one department** within an hour. Leadership fears ransomware; alternatively, it could be a **bad patch** or a **shared infected USB**. Your task is to distinguish **mass infection** from **lateral movement** and set the response tempo.

### Investigation Objectives
- Determine whether detections share a **common delivery mechanism** (email, share, update).
- Map **lateral paths** (SMB/RDP/WMI) vs **parallel infections**.
- Identify **patient zero** candidates using timestamps.
- Recommend **containment tiers** (isolate subnet, disable accounts, block IOCs).

### Logs/Artifacts Description
You have access to:

- **EDR alerts** across hosts with hashes and file paths.
- **Network connection logs** between internal hosts.
- **Email logs** (optional) for the same department.
- **Patch management logs** (optional) for the same window.

### Tasks
1. **Cluster hosts**
   - Same malware family vs different families.
2. **Timeline**
   - Earliest execution per host; identify first mover.
3. **Movement hypothesis**
   - Single admin tool spreading vs parallel downloads.
4. **Containment**
   - Minimum effective actions to stop spread.
5. **Comms**
   - Status update template for IT managers.

### Questions
- What pattern would convince you this is lateral movement?
- When would you isolate a VLAN vs individual hosts?
- How do you avoid destroying evidence during containment?

### Indicators of Compromise
Consolidate:

- Hashes, C2 domains, internal IPs involved in lateral sessions, accounts used.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Differentiate parallel outbreaks from lateral movement using timelines and network context.
