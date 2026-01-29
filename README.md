# Clinical Trial Disclosure & Compliance Intelligence  
**Snowflake Marketplace Data Product**

---

## Overview

**Clinical Trial Disclosure & Compliance Intelligence** is a curated, analytics-ready dataset designed to help life sciences organizations monitor, benchmark, and reduce regulatory disclosure risk across the global clinical trial ecosystem.

This product provides trial-level compliance scoring, sponsor-level disclosure benchmarking, integrity risk indicators, and alert-ready outputs built from structured ClinicalTrials.gov trial metadata.

It is optimized for direct consumption inside Snowflake and is delivered through a secure Snowflake Marketplace share.

---

## Key Enterprise Use Cases

This dataset supports high-impact regulatory and operational workflows including:

- **FDAAA 801 results reporting compliance monitoring**
- **Identification of overdue or missing clinical trial results**
- **Sponsor disclosure performance benchmarking**
- **Clinical trial execution integrity and dropout risk analysis**
- **Adverse event burden and safety risk monitoring**
- **Trial transparency and audit-ready reporting**
- **CRO and partner diligence scoring**

---

## What’s Included

This Marketplace listing includes six curated secure analytical views:

| View Name | Description |
|----------|-------------|
| `FACT_TRIAL_COMPLIANCE` | Trial-level compliance status and disclosure risk scoring |
| `FACT_SPONSOR_COMPLIANCE` | Sponsor-level reporting success and delay benchmarking |
| `FACT_COMPLIANCE_ALERT_QUEUE` | Actionable queue of high-risk or overdue compliance trials |
| `FACT_TRIAL_INTEGRITY` | Execution integrity scoring using dropout + AE + retraction flags |
| `FACT_SPONSOR_TRUST_SCORE` | Composite sponsor trust benchmark (0–100) |
| `BRIDGE_TRIAL_PUBLICATIONS` | Trial-to-publication linkage (NCT → PMID transparency bridge) |

---

## View Details

---

### 1. `FACT_TRIAL_COMPLIANCE`

Provides trial-level disclosure compliance status and risk scoring.

Key fields include:

- `COMPLIANCE_STATUS`
  - `VIOLATION`
  - `MISSING_RESULTS_OVERDUE`
  - `LATE_REPORTED`
  - `REPORTED`

- `COMPLIANCE_RISK_SCORE` (0–100)

Example query:

```sql
SELECT *
FROM FACT_TRIAL_COMPLIANCE
WHERE COMPLIANCE_STATUS = 'MISSING_RESULTS_OVERDUE'
ORDER BY COMPLIANCE_RISK_SCORE DESC;
