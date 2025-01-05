## Lab 38 – Threat Analysis: Phishing Campaign Clustering

### Scenario
Several phishing waves have hit your organisation with similar lures and sender patterns. Your task is to **cluster** related messages, extract shared infrastructure, and produce a **single IOC list** for blocking and awareness.

### Investigation Objectives
- Group messages by **shared indicators** (domain, URL path, attachment hash, reply-to).
- Separate **multiple campaigns** if infrastructure diverges.
- Prioritise IOCs for **fast blocking** vs **monitoring**.
- Draft a **short user awareness** bullet (non-technical).

### Logs/Artifacts Description
You have access to:

- **Email security logs**:
  - Message IDs, sender, return-path, links, attachment hashes, delivery status.
- **Sandbox summaries** (optional): attachment behaviour families.

### Tasks
1. **Normalise fields**
   - Extract domains, URLs, hashes into a table.
2. **Cluster**
   - Use at least two clustering keys (for example domain + subject pattern).
3. **Name the campaign**
   - Internal codename and date range.
4. **IOC package**
   - Minimum viable list for SOC and mail teams.
5. **Recommendations**
   - Mail rule, URL rewrite tuning, DMARC discussion points.

### Questions
- How do you avoid blocking legitimate senders that look similar?
- What indicates two campaigns vs one with rotating infrastructure?
- What would you measure after deploying new blocks?

### Indicators of Compromise
Include:

- Senders, domains, URLs, attachment hashes, and any shared IP from headers.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Cluster phishing activity and publish actionable IOCs.
