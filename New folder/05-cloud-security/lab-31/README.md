## Lab 31 – Cloud: Suspicious Cloud Console Login (Intermediate)

### Scenario
Your organisation uses a major public cloud provider. The security dashboard shows a **successful console login** from an unusual region to an administrative account that normally signs in from a different country. Shortly after login, IAM changes occurred. You must determine whether this is **compromise** or **travel/admin work**.

### Investigation Objectives
- Validate whether the login fits **historical patterns** for that identity.
- Enumerate **actions after authentication** (IAM, keys, logging changes).
- Assess **MFA and session** signals (if present).
- Recommend **containment** for identity and cloud tenancy.

### Logs/Artifacts Description
You have access to:

- **Cloud sign-in / audit logs**:
  - Principal, IP, user agent, MFA result, region, time.
- **IAM change events**:
  - Policies attached, users created, roles modified.
- **Cloud security alerts** tied to the same session.

### Tasks
1. **Timeline the session**
   - Login through last privileged action.
2. **Compare to baseline**
   - Typical countries, times, and devices for this admin.
3. **Identify risky changes**
   - Over-privileged policies, new users, disabled logging.
4. **Correlate with corporate identity**
   - VPN/SSO overlap or absence.
5. **Response**
   - Session revoke, key rotation, forced MFA reset, break-glass process.

### Questions
- What single IAM change would force immediate tenant-wide incident response?
- How do you distinguish travel from token theft?
- What would you ask the user on a verification call (without accusing)?

### Indicators of Compromise
Record:

- Source IP, ASN/region, user agent, IAM change IDs, new credentials created.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Investigate privileged cloud sessions using audit-first analysis.
