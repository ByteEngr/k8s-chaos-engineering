## Lab 21 – Network: Distinguishing Scanning vs Targeted Attack

### Scenario
The IDS reports “port scan” from an external IP. Some servers show denies; one shows a few allows to non-standard ports. You must decide if this is **internet-wide scanning** or a **focused attempt** against your organisation.

### Investigation Objectives
- Compare **breadth vs depth** of activity (many IPs touched vs few IPs with many attempts).
- Analyse **timing and persistence** of the source.
- Correlate with **successful authentication** or **application errors** if available.
- Recommend **watch vs block** decisions.

### Logs/Artifacts Description
You have access to:

- **IDS alerts** with scan type and target list.
- **Firewall session logs** with hit counts per internal destination.
- **WAF or application logs** (optional) for targeted hosts.

### Tasks
1. **Profile the source**
   - Single IP vs rotating pool; known scanner ASN vs residential mix.
2. **Target distribution**
   - Random high ports vs your published service ports.
3. **Success indicators**
   - Look for allows, HTTP 200s, or auth failures on targeted services.
4. **Hypothesis**
   - Background scan vs reconnaissance before exploitation.
5. **Response**
   - Block duration, alerting rule, and owner notification list.

### Questions
- What is your threshold for “targeted” in your environment?
- How would you verify if the same actor hit other organisations (conceptually)?
- When do you escalate to incident response vs NOC?

### Indicators of Compromise
Record:

- Source IP/ASN, targeted ports, and any successful session identifiers.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Differentiate opportunistic scanning from more deliberate targeting using log patterns.
