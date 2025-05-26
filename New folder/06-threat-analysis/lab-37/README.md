## Lab 37 – Threat Analysis: Building an IOC Cluster (Intermediate)

### Scenario
Over the past week, your SOC has observed several seemingly unrelated alerts across different customers: phishing emails, endpoint malware detections, and outbound connections to unfamiliar domains. You suspect these may be part of a single threat campaign. Your task is to **analyse and cluster IOCs** to determine whether they form a coherent threat actor or campaign.

### Investigation Objectives
- Aggregate IOCs from multiple cases (emails, endpoints, and network alerts).
- Identify patterns that suggest a common campaign (infrastructure, tooling, or tradecraft).
- Propose a campaign profile that can be shared with the wider team.

### Logs/Artifacts Description
You have access to:

- **Phishing case data**:
  - Sender addresses, subject lines, attachment names, and URLs.
- **Endpoint alerts**:
  - Malware detection names, file hashes, and file paths.
- **Network telemetry**:
  - Destination IPs/domains, ports, and SSL certificate metadata where available.

Artifacts may be collected from multiple tickets or exported from different tools.

### Tasks
1. **Collect and normalise IOCs**
   - Gather IOCs from the various alerts into a single working list:
     - Email senders, URLs, and attachment names.
     - File hashes from endpoints.
     - Domains and IPs from network alerts.
2. **Cluster by similarity**
   - Group IOCs by:
     - Shared domains or IP ranges.
     - Reused file names or similar naming patterns.
     - Common timing or targeted user groups.
3. **Enrich key indicators**
   - For a subset of IOCs, conceptually perform threat‑intel enrichment:
     - Check whether domains/IPs share infrastructure.
     - Look for references to known malware families or campaigns.
4. **Define a campaign hypothesis**
   - Based on patterns, propose:
     - Whether there is likely a single underlying campaign.
     - What its probable goals are (credential theft, data theft, ransomware staging, etc.).
5. **Document detection and hunting ideas**
   - Suggest new rules or hunts that would detect future activity from this campaign.

### Questions
- Which IOCs appear across multiple cases or data sources?
- What common infrastructure (domains, IP ranges, certificates) is being reused?
- Do the attachment names, email lures, or malware families point to a consistent theme?
- How confident are you that these cases belong to a single threat campaign?
- What additional data would increase your confidence?

### Indicators of Compromise
Produce an organised IOC set, segmented into:

- **Email IOCs** – senders, subjects, URLs, attachment names.
- **Endpoint IOCs** – file hashes, file names, paths.
- **Network IOCs** – IPs, domains, ports, certificates.

Highlight IOCs that appear to be **campaign‑level** rather than single‑case.

### Expected Analyst Outcome
By the end of this lab, a junior threat analyst should be able to:

- Consolidate IOCs from disparate alerts into a unified view.
- Identify patterns that suggest a shared campaign.
- Produce a concise campaign profile and IOC set that can be shared for detection and hunting.

