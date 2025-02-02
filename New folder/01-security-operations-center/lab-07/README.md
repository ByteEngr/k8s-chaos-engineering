## Lab 07 – SOC: Cross-Source Correlation (SIEM, DNS, Proxy)

### Scenario
A single SIEM alert points to a workstation contacting a low-reputation domain. Your task is to **correlate** that alert with DNS and proxy logs for the same time window, find other hosts that contacted the same infrastructure, and recommend whether this is an isolated incident or a broader campaign.

### Investigation Objectives
- Validate the SIEM IOC against **ground truth** in DNS and HTTP(S) metadata.
- Search for **other internal clients** resolving or requesting the same indicators.
- Characterise the **traffic**: browser download, background updater, or scripted beaconing.
- Decide whether to **hunt org-wide** on the IOC set.

### Logs/Artifacts Description
You have access to:

- **SIEM alert** with destination domain/IP and first/last seen.
- **DNS resolver logs** (corporate resolver):
  - Client IP, query name, response, TTL, timestamp.
- **Proxy or secure web gateway logs**:
  - URL, category, action, bytes, user ID if authenticated.
- **Optional**: passive DNS or threat intel lookup notes (conceptual).

### Tasks
1. **Confirm the chain**
   - Show DNS query then connection to the same host where possible.
2. **Expand horizontally**
   - Search the same domain/IP across all clients in the last 7 days.
3. **Classify behaviour**
   - Decide if activity looks like user-driven browsing vs automated callback.
4. **Campaign assessment**
   - If multiple hosts hit the same infrastructure, outline a mini hunt scope.
5. **Response**
   - Recommend block vs monitor vs host isolation per risk.

### Questions
- What evidence proves the SIEM alert is not a parser or time skew error?
- How many hosts would trigger an org-wide hunt in your team’s culture?
- What benign explanation would you test before declaring malicious?

### Indicators of Compromise
Produce a **correlation package**:

- Domains, IPs, URL paths, and any file hash from proxy metadata.
- List of internal hosts observed (redact if needed in a classroom setting).

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Pivot confidently across SIEM, DNS, and proxy data.
- Distinguish one-off events from distributed activity.
- Recommend scoped containment and detection improvements.
