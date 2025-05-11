## Lab 05 – SOC: Weekend Handoff and Context Preservation

### Scenario
You are taking over the weekend shift. The outgoing analyst leaves a sparse handoff: “Check queue, lots of duplicates.” Your task is to **normalise** the open items, preserve **investigation context** for Monday, and ensure nothing high severity is buried in duplicate tickets.

### Investigation Objectives
- Merge or link **duplicate tickets** that describe the same root cause.
- Produce a **handoff note** with status per incident thread (new, active, waiting, closed).
- Flag any item needing **Monday ownership** (legal hold, vendor follow-up, rule tuning).
- Confirm **SLA risk** for anything nearing breach.

### Logs/Artifacts Description
You have access to:

- **Ticketing system export**:
  - Ticket ID, title, severity, assignee, created time, last update, tags.
- **SIEM alert IDs** referenced in ticket bodies (free text).
- **Optional**: a deduplication hint table mapping alert fingerprint to ticket IDs.

### Tasks
1. **Group duplicates**
   - Use alert type + host + 1-hour window as a starting heuristic.
2. **Pick a parent ticket**
   - For each group, choose the best parent and list child tickets to merge or link.
3. **Write a shift log**
   - Timestamped entries for actions taken overnight.
4. **Surface escalations**
   - List anything that must be visible at shift change (customer-facing, exec asset, critical server).
5. **Leave actionable next steps**
   - For each open parent ticket: owner, next command or log to pull, deadline.

### Questions
- How do you avoid losing nuance when merging tickets?
- What metadata should every parent ticket always contain after your handoff?
- When would you **not** merge two similar-looking tickets?

### Indicators of Compromise
Where duplicates exist, consolidate IOCs into one **master list** per incident thread:

- Hostname, user, hashes, domains, IPs (deduplicated).

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Clean up duplicate work without deleting audit history.
- Produce a professional handoff that reduces Monday rework.
- Prioritise continuity over personal ticket counts.
