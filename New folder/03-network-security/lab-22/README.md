## Lab 22 – Network: Proxy and Web Gateway Log Correlation

### Scenario
Users report slow browsing; the proxy team sees elevated blocks. Security wants to know if blocks are **policy enforcement** or signs of **malware C2 over HTTPS**. Your task is to correlate **user identity**, **categories**, and **destination reputation** to decide.

### Investigation Objectives
- Identify **top blocked categories** and whether they cluster by department.
- Find **repeat offenders** (users or hosts) vs one-off mistakes.
- Spot **unusual uncategorised domains** or **newly seen destinations**.
- Recommend **user education** vs **technical controls**.

### Logs/Artifacts Description
You have access to:

- **Secure web gateway logs**:
  - User, group, URL, category, action, bytes, time.
- **DNS logs** (optional) for the same clients.
- **EDR alerts** (optional) if provided for the same hosts.

### Tasks
1. **Segment by user and department**
   - Find outliers compared to peers.
2. **Review uncategorised URLs**
   - Flag random subdomains or URL shorteners.
3. **Correlate with endpoint**
   - See if blocks align with suspicious processes.
4. **Policy recommendation**
   - Tighter category, SSL inspection scope discussion, or exception process.
5. **Communication**
   - Draft a non-technical explanation for one business unit.

### Questions
- When is heavy blocking a sign of infection vs policy mismatch?
- What privacy constraints affect SSL inspection decisions?
- How do you avoid blaming users in your report?

### Indicators of Compromise
Capture:

- Domains and URL paths that appear across multiple hosts.
- User agents or JA3-style fingerprints if your logs include them (conceptual).

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Use proxy telemetry for both policy and security investigations.
