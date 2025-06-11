## Lab 04 – SOC: False Positive Review and Tuning

### Scenario
Tier-2 has returned several tickets marked “benign” after deep dives. The SOC manager wants a **false-positive review** for one noisy detection rule: repeated DNS queries to newly registered domains from developer workstations. Your job is to analyse sample closures, decide if the rule is still valuable, and suggest **tuning** ideas (thresholds, exclusions, or enrichment).

### Investigation Objectives
- Summarise **why** past alerts were closed as false positives.
- Identify **patterns** in benign traffic (build pipelines, IDE plugins, research).
- Propose **specific tuning** changes that reduce noise without hiding real threats.
- List **risks** of each tuning option.

### Logs/Artifacts Description
You have access to:

- **Closed ticket summaries** (10–20 rows):
  - Original alert fields, closure reason, analyst comments.
- **Sample DNS logs** for closed cases:
  - Query name, response, client IP, frequency.
- **Asset context**:
  - Role tags (developer, finance, guest) per workstation.

### Tasks
1. **Bucket closure reasons**
   - Group tickets into categories (IDE, browser extension, security research, etc.).
2. **Find common benign domains or TLD patterns**
   - Note repeats that could be allowlisted with governance.
3. **Propose rule changes**
   - For example: higher threshold for dev VLANs, enrich with proxy category, require rare domain + non-browser process.
4. **Define a validation plan**
   - How you would measure noise reduction after a change.
5. **Draft a short note to detection engineering**
   - Bullet list: change, expected impact, rollback plan.

### Questions
- Which exclusions would you **never** apply globally without strong governance?
- How would you prove the rule still catches real malware after tuning?
- What stakeholder (IT, dev leads) should approve dev-network exceptions?

### Indicators of Compromise
Even in an FP review, record **features** that should stay suspicious, for example:

- DNS queries from non-developer VLANs to the same rare domains.
- Coupling of rare DNS with unexpected child processes.

### Expected Analyst Outcome
By the end of this lab, a junior SOC analyst should be able to:

- Analyse false-positive trends and translate them into tuning recommendations.
- Balance analyst workload with detection coverage.
- Communicate changes clearly to engineering and management.
