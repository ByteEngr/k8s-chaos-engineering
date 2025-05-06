## Lab 20 – Network: Denied Connection Spike Analysis

### Scenario
Monitoring shows a **spike in denied connections** at the perimeter. Leadership worries about an attack; the firewall admin thinks it is background internet noise. Your task is to determine whether the spike is **targeted**, **distributed scanning**, or **misconfiguration**, and whether any allows slipped through.

### Investigation Objectives
- Plot **volume over time** and compare to baseline.
- Identify **top source countries/ASNs** and **top destination ports**.
- Check for **any allows** in the same window that deserve priority review.
- Recommend **rate limits or geo blocks** if appropriate.

### Logs/Artifacts Description
You have access to:

- **Firewall deny logs** (aggregated): count by minute, source IP, dest IP, port.
- **Allow logs sample** for the same window.
- **Threat feed enrichment** (conceptual) for top sources.

### Tasks
1. **Baseline comparison**
   - Compare spike day vs prior week same weekday.
2. **Top talkers**
   - List top external sources and whether they hit many internal IPs or one VIP.
3. **Port analysis**
   - Interpret port focus (for example 445 vs 22 vs 3389).
4. **Allow path review**
   - Spot unusual allows that correlate in time with denies.
5. **Conclusion**
   - Attack campaign vs internet background vs misconfigured probe.

### Questions
- How do you explain to non-experts why denies can be noisy but still important?
- What would trigger an immediate escalation despite mostly denies?
- What dashboard would you build to watch this weekly?

### Indicators of Compromise
Extract **actionable IOCs**:

- Source IPs or nets worth temporary blocking.
- Destination ports that suggest targeted probing of your services.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Interpret deny spikes without mistaking noise for a breach.
