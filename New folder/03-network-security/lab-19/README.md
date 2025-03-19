## Lab 19 – Network: Firewall Rule and IDS Tuning

### Scenario
The IDS has fired thousands of alerts on a signature that often matches internal vulnerability scans. The firewall team says the rule is noisy but occasionally catches real exploits. Your task is to **review tuning options**: thresholding, suppression, scope limits, and verification steps after change.

### Investigation Objectives
- Quantify **noise** (false positive rate, affected subnets, time of day).
- Identify **true positive characteristics** that must be preserved.
- Propose **safe tuning** (per subnet, per destination, threshold, severity mapping).
- Define a **test plan** to validate tuning in lower environments.

### Logs/Artifacts Description
You have access to:

- **IDS alert export** (30 days): signature ID, source, dest, count, payload snippet flags.
- **Change tickets** referencing approved scans or pen tests.
- **Firewall policy map** showing which segments are internet-facing vs internal.

### Tasks
1. **Segment alerts**
   - Split scan-related vs exploit attempt patterns.
2. **Correlate with authorised activity**
   - Match source IPs to known scanners or vuln tools.
3. **Draft tuning**
   - Propose signature exceptions with narrow scope.
4. **Risk statement**
   - What you might miss after tuning and how to compensate.
5. **Sign-off package**
   - Who must approve (security, network, compliance).

### Questions
- When is suppression better than disabling a signature?
- How do you detect when a tuned signature suddenly becomes relevant again?
- What metric proves tuning helped?

### Indicators of Compromise
Even when tuning, keep a list of **IOC patterns** that must never be suppressed globally:

- Rare external sources, unexpected internal sources, successful exploit follow-on traffic.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Partner with network engineering on sustainable detection tuning.
