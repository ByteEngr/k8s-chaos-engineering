## Lab 13 – Endpoint: EDR Telemetry and Network Connections

### Scenario
An endpoint has generated a low-severity alert, but the same host shows **bursty outbound connections** to several countries. Your task is to correlate **EDR process telemetry** with **network connection events** from the agent and decide if this is benign sync traffic, misconfigured software, or command-and-control behaviour.

### Investigation Objectives
- Identify which **processes** own the outbound connections.
- Map connections to **destination reputation** (conceptual categories).
- Determine if **volume and timing** match a known benign pattern.
- Decide whether to **isolate** the host pending deeper analysis.

### Logs/Artifacts Description
You have access to:

- **EDR network connection events**:
  - Process name, PID, destination IP/domain, port, byte counts, timestamps.
- **Process tree / command line** for the same window.
- **DNS client events** from the endpoint if available.

### Tasks
1. **Sort connections by process**
   - Identify top talkers by byte count and connection count.
2. **Inspect parents**
   - Confirm the process is expected (for example browser vs unknown binary).
3. **Time correlation**
   - Plot bursts against user login or scheduled tasks.
4. **Reputation triage**
   - Flag destinations that are rare for your organisation.
5. **Containment decision**
   - Isolate or escalate with a short justification.

### Questions
- What pattern separates a cloud updater from beaconing?
- When would you trust bytes-up vs bytes-down?
- What would you ask the network team to validate at the firewall?

### Indicators of Compromise
List:

- Destination IPs/domains, ports, and process image paths.
- Any self-signed or unusual binary paths.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Join process context to network behaviour on an endpoint.
- Make a proportionate containment decision.
