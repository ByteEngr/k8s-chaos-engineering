## Lab 15 – Endpoint: Isolation Decision and Remediation Handoff

### Scenario
The endpoint team can **isolate** hosts from the network in one click, but doing so disrupts executives and operational staff. A serious infection is suspected but not fully confirmed. Your task is to decide **if/when to isolate**, what evidence to capture first, and how to **hand off** to remediation.

### Investigation Objectives
- List **criteria** for immediate isolation vs delayed isolation.
- Decide what **evidence** to preserve before isolation (memory, disk snapshot, logs).
- Draft a **remediation handoff** with owners and steps.
- Plan **return-to-service** checks.

### Logs/Artifacts Description
You have access to:

- **EDR full incident** (alerts, behaviours, files).
- **Asset criticality** (role-based tags).
- **Change calendar** (optional) to avoid isolating during a maintenance freeze.

### Tasks
1. **Risk vs impact**
   - Score the infection risk against business impact of isolation.
2. **Pre-isolation checklist**
   - What to export or snapshot if policy allows.
3. **Isolation decision**
   - Document yes/no and timing.
4. **Handoff package**
   - What Tier-2 or IT needs to re-image or restore.
5. **Communication**
   - User-facing message template (no technical jargon).

### Questions
- Under what conditions would you isolate without management approval?
- What mistakes make isolation worse than useful?
- How do you prove a host is clean before reconnecting?

### Indicators of Compromise
Include in the handoff:

- Key IOCs, timeline, affected user, data sensitivity tag.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Make isolation decisions with clear criteria and documentation.
- Hand off remediation work without losing critical context.
