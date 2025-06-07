## Lab 06 – SOC: High-Volume Day and Queue Prioritisation

### Scenario
A marketing campaign and a VPN outage have spiked alert volume. The queue shows hundreds of items; many are informational. You must **triage at scale**: apply a repeatable prioritisation method, clear noise safely, and protect time for a handful of genuine incidents.

### Investigation Objectives
- Define **priority tiers** (for example P1–P4) using severity, asset criticality, and blast radius.
- Identify **bulk benign patterns** that can be bulk-closed with documentation.
- Select **top N** items for immediate human review.
- Estimate **capacity**: what fits in one hour vs what must wait.

### Logs/Artifacts Description
You have access to:

- **SIEM queue snapshot**:
  - Columns: rule, severity, MITRE tag (if any), source asset criticality, event count.
- **Asset inventory snippet**:
  - Criticality tier for servers and admin jump hosts.
- **Known noisy rule list** from last month’s tuning notes.

### Tasks
1. **Sort and filter**
   - Filter out known noisy rules that already have an approved suppression window.
2. **Score items**
   - Assign each remaining alert a priority score using your tier table.
3. **Batch benign closures**
   - Where safe, propose a single closure reason for a class of alerts (documented).
4. **Pick your hour-one list**
   - The five tickets you would open first and why.
5. **Communicate risk**
   - One paragraph for the lead: what you deferred and why it is probably OK.

### Questions
- What is your rule for never bulk-closing without a second pair of eyes?
- How do you handle two P1s with only one analyst available?
- What metric would you track to prove the queue process improved?

### Indicators of Compromise
For items you escalate, capture **fast IOCs** only:

- External IP/domain, hash, or account name worth blocking or hunting.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Operate under high volume without chasing every alert equally.
- Document defensible bulk actions.
- Communicate deferred risk transparently.
