## Lab 44 – Threat Investigation & Response: Business Email Compromise

### Scenario
Finance reports a vendor payment was redirected after an email thread about invoice updates. Your task is to **investigate** the email path, identify where the attacker inserted themselves, and document **IOCs and recovery steps** for legal and banking partners.

### Investigation Objectives
- Determine whether the compromise is **inbox-level** (vendor), **spoofing**, or **internal mailbox** abuse.
- Reconstruct the **email hop timeline** (headers, authentication results).
- Identify **fraudulent bank details** and when they appeared.
- Recommend **immediate containment** (password resets, mailbox rules review, vendor contact).

### Logs/Artifacts Description
You have access to:

- **Email headers and authentication results** (SPF/DKIM/DMARC as available).
- **Message trace / delivery logs** for affected users.
- **Mailbox rule audit** (forwarding, inbox rules).
- **Optional**: vendor compromise indicators from their IT (simulated statement).

### Tasks
1. **Trace the thread**
   - First legitimate message vs first attacker-controlled message.
2. **Authentication analysis**
   - Spoof vs compromised account indicators.
3. **Mailbox inspection**
   - Hidden rules, forwarding, delegate access.
4. **Financial impact triage**
   - What was paid, to which account, and reporting deadlines.
5. **Response plan**
   - User actions, vendor verification process, law enforcement considerations (high level).

### Questions
- What header signals strongest indicate direct inbox compromise vs display-name spoofing?
- What would you ask the vendor to verify out-of-band?
- What evidence do you preserve for legal and insurance?

### Indicators of Compromise
Record:

- Sending IPs, return-path domains, fraudulent bank accounts, malicious domains in links.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate BEC with an evidence chain suitable for stakeholders beyond IT.
