## Lab 14 – Endpoint: Scope Assessment After Detection

### Scenario
A workstation has a confirmed malware detection. Before re-imaging, leadership asks: **how far did this spread?** Your task is to define **scope**: other hosts, accounts, or shares that may be affected, using EDR and identity logs.

### Investigation Objectives
- Identify **patient zero** and **initial access time** if possible.
- Enumerate **lateral movement indicators** (shared credentials, SMB, RDP, WMI).
- Recommend **hunt queries** for other endpoints.
- Produce a **scope statement** for incident command.

### Logs/Artifacts Description
You have access to:

- **EDR alerts and events** on the affected host.
- **Authentication logs** (AD or IdP): logons from the same user to other hosts.
- **File share / SMB access** logs if available.

### Tasks
1. **Build a timeline**
   - First suspicious execution through last observed activity.
2. **Account review**
   - List accounts used on the host and any suspicious logons elsewhere.
3. **Network pivots**
   - Find other hosts contacted by the same internal IPs or named pipes.
4. **Define hunt scope**
   - Org units, VLANs, or device groups to sweep.
5. **Communicate uncertainty**
   - What you know vs what requires full IR.

### Questions
- What is the minimum evidence you need before declaring “contained”?
- How do you avoid over-scoping a hunt that burns the team?
- What would Tier-2 do that Tier-1 cannot for scope?

### Indicators of Compromise
Consolidate IOCs suitable for **org-wide hunts**:

- Hashes, service names, domains, registry keys, or LOLBin command lines.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Translate a single-host detection into a controlled scope assessment.
