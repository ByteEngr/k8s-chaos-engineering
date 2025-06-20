## Lab 41 – Threat Analysis: IOC Validation and Scope

### Scenario
A vendor feed published IOCs tied to an active campaign. Before blocking broadly, you must **validate** which IOCs are still live, which are benign in your environment, and what **scope** of assets to hunt.

### Investigation Objectives
- Test IOCs against **internal telemetry** (last seen dates, prevalence).
- Identify **false positives** or stale indicators.
- Define **hunt scope** (business units, time window, log sources).
- Produce a **validated deployment list** for SOC tools.

### Logs/Artifacts Description
You have access to:

- **Threat feed IOC list** (domains, IPs, hashes).
- **Internal SIIM search results** (simulated): hit counts per IOC.
- **Change calendar**: known upgrades that could explain hits.

### Tasks
1. **Mark each IOC**
   - Active / stale / benign / needs more data.
2. **Investigate top hits**
   - Determine if hits are security tools, scanners, or real malware.
3. **Scope hunts**
   - Prioritise crown-jewel systems first.
4. **Safe blocking**
   - Recommend blocks only where impact is understood.
5. **Feedback to intel**
   - What to remove from the feed list.

### Questions
- What validation step prevents blocking your own security scanners?
- How long should you observe before declaring stale?
- Who approves enterprise-wide blocks?

### Indicators of Compromise
Output:

- A **curated** IOC list with validation notes per item.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Operationalise threat intelligence without breaking the business.
