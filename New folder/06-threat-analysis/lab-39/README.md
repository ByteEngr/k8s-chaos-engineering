## Lab 39 – Threat Analysis: IOC Enrichment and Overlap

### Scenario
Endpoint and network IOCs from different cases share overlapping domains and IPs. Your task is to **enrich** indicators (conceptually: WHOIS, passive DNS, ASN context) and decide whether they belong to **one infrastructure set** or coincidental overlap.

### Investigation Objectives
- Enrich each IOC with **ownership and age** signals (as available).
- Build an **overlap graph**: which IOCs share registrants, subnets, or certificates.
- Decide which overlaps are **strong** vs **weak** evidence.
- Recommend **priority enrichment** for the most uncertain indicators.

### Logs/Artifacts Description
You have access to:

- **IOC spreadsheet** from multiple tickets:
  - Domains, IPs, hashes, first seen dates.
- **Enrichment notes** (simulated) for WHOIS and ASN.

### Tasks
1. **Deduplicate**
   - Normalise domains (punycode, case).
2. **Enrich**
   - Add ASN, country, registration age where applicable.
3. **Overlap analysis**
   - Identify shared /24s or shared name servers (if present).
4. **Conclusion**
   - Single operator vs commodity infrastructure.
5. **Next steps**
   - Which IOCs to block vs hunt internally.

### Questions
- When does shared hosting make IP overlap meaningless?
- What enrichment sources can mislead analysts?
- How do you document uncertainty?

### Indicators of Compromise
Produce a **merged IOC list** with confidence tags:

- High / medium / low confidence per indicator.

### Expected Analyst Outcome
By the end of this lab, a junior analyst should be able to:

- Use enrichment to strengthen or weaken clustering hypotheses.
