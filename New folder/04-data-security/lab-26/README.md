## Lab 26 – Data: DLP and USB Copy Attempt

### Scenario
DLP alerts show a user attempted to copy sensitive project files to a **USB device** that is not on the approved encryption standard. HR is involved because the files are customer contracts. Your task is to determine **intent**, **scope**, and **response**.

### Investigation Objectives
- Confirm **what was attempted** (blocked vs successful, full file vs partial).
- Identify **device class** and policy that triggered.
- Assess whether this matches **normal job duties** or policy violation.
- Recommend **user action** (coaching) vs **security escalation**.

### Logs/Artifacts Description
You have access to:

- **DLP endpoint events**:
  - Policy name, action, file classification, path patterns, user, device ID.
- **USB device inventory**:
  - Serial, vendor, encryption status if reported.
- **Optional HR/ticket context** (simulated): travel, new laptop migration.

### Tasks
1. **Validate sequence**
   - Attempts over time; any successful copy to other destinations?
2. **Classification check**
   - Which labels fired and were they appropriate?
3. **Policy alignment**
   - Should this user role have an exception process?
4. **Response plan**
   - Revoke device, re-image, legal review triggers.
5. **Documentation**
   - Facts only, suitable for HR review.

### Questions
- What is the minimum evidence before involving HR?
- How do you avoid false confidence when DLP cannot see file contents?
- What alternative transfer methods would you check next?

### Indicators of Compromise
Record:

- Device identifiers, file share paths, DLP policy names, and user ID.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate DLP USB events with proportionate response.
