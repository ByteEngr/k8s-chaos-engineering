## Lab 28 – Data: Internal Collaboration and External Share

### Scenario
A sensitive engineering package was shared via the company’s **collaboration platform** with an **external email address** that looks like a personal mailbox. Your task is to review sharing events, permissions, and whether the external party is authorised.

### Investigation Objectives
- List **sharing events** (who shared, what resource, permissions, expiry).
- Validate **recipient legitimacy** (vendor contract, typo, unknown domain).
- Determine if **link settings** are too permissive (anyone with link).
- Recommend **revocation** and **audit** steps.

### Logs/Artifacts Description
You have access to:

- **Collaboration audit logs**:
  - Share created, link type, guest user invited, IP of creator.
- **Identity logs**:
  - SSO sign-in for the sharing user.
- **Optional**: procurement/vendor list for expected domains.

### Tasks
1. **Reconstruct the share**
   - Folder/file, permission model, expiration.
2. **Recipient review**
   - Compare domain to approved vendor domains.
3. **Risk**
   - Read-only vs edit; public link vs named guest.
4. **Response**
   - Revoke, re-issue with correct controls, notify data owner.
5. **Prevention**
   - DLP rule ideas and training nudges.

### Questions
- What proves intentional sharing vs accidental autocomplete?
- How do you work with the data owner without blaming them?
- What would you monitor after revocation?

### Indicators of Compromise
Record:

- External email addresses (redacted in class), share IDs, resource names, creator UPN.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate external sharing with audit-first thinking.
