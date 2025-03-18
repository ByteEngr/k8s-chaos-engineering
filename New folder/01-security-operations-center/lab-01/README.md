## Lab 01 – SOC: Initial Alert Triage (Basic)

### Scenario
You are a Tier‑1 analyst in a regional Security Operations Center supporting a mid‑size financial services company. The SIEM has generated multiple alerts for suspicious outbound connections from a single workstation during business hours. The duty lead has assigned you to **triage** the alerts, determine whether they represent a true security event, and decide whether to escalate to Tier‑2.

### Investigation Objectives
- Determine whether the SIEM alert represents:
  - A false positive,
  - A benign but notable event, or
  - A true security incident requiring escalation.
- Identify the **affected asset**, **user**, and **time window** involved.
- Identify any **related alerts** that might indicate a broader issue.

### Logs/Artifacts Description
For this lab, you have access to:

- **SIEM alerts and correlated events**:
  - Alert type: “Suspicious outbound connection to low‑reputation domain”.
  - Fields: source IP, source user, destination IP/domain, destination port, rule name, severity, first/last seen.
- **DNS logs**:
  - Query/response pairs for the suspicious domains.
  - Timestamps and client IP addresses.
- **Proxy or web gateway logs**:
  - HTTP(S) requests made by the workstation.
  - URLs, categories, and HTTP response codes.

Assume these artifacts are accessible in your lab SIEM or as exported CSV/JSON files.

### Tasks
1. **Review the SIEM alert details**
   - Identify the rule that fired, its severity, and the number of events involved.
   - Extract the source IP, user, and time range of activity.
2. **Pivot into DNS and proxy logs**
   - Search for all DNS queries from the source IP around the time of the alert.
   - Identify which domains were resolved and whether they match the SIEM IOCs.
   - In proxy logs, look for URLs associated with the suspicious domains.
3. **Assess reputation and context**
   - For each suspicious domain or IP, check reputation (conceptually or using your preferred tools).
   - Look for patterns such as:
     - Uncommon TLDs,
     - Newly registered domains,
     - Random‑looking subdomains.
4. **Look for related alerts**
   - Check whether other hosts or users have generated similar alerts.
   - Determine whether this is a single‑host issue or part of a broader pattern.
5. **Decide on escalation**
   - Based on evidence, decide if this should be:
     - Closed as benign,
     - Closed with monitoring,
     - Escalated to Tier‑2 for deeper endpoint or forensic investigation.

### Questions
- Which **host** and **user** triggered the original alert?
- What were the **suspicious domains or IPs**, and how often were they contacted?
- Did any other hosts display similar behaviour in the same time window?
- What factors influenced your decision to escalate or close the case?
- How would you document this triage in a ticketing system?

### Indicators of Compromise
During this lab, identify and record all potential IOCs, such as:

- Suspicious destination IP addresses.
- Suspicious or newly registered domains.
- Unusual URL paths or user‑agent strings (if available).

Clearly distinguish between **confirmed malicious**, **suspicious**, and **benign** indicators based on your findings.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Extract key fields from SIEM alerts and associated logs.
- Correlate SIEM alerts with DNS and proxy activity for a single host.
- Make and justify an escalation decision based on available evidence.
- Document findings, identified IOCs, and next steps in an investigation ticket.

