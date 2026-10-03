# ✅ Control Tests

> 4 control test records, each run against a specific sample rather than a general check.

| # | Control | Test Date | Result | Tester |
|---|---|---|---|---|
| 1 | Multi-Factor Authentication for Administrative Access | 2026-09-10 | ![Partial](https://img.shields.io/badge/result-Partial-dbab09) | Augustine Ozor |
| 2 | Encryption of Customer Data at Rest and in Transit | 2026-09-11 | ![Pass](https://img.shields.io/badge/result-Pass-28a745) | Augustine Ozor |
| 3 | Code Change Review and CI/CD Gate Enforcement | 2026-09-12 | ![Pass](https://img.shields.io/badge/result-Pass-28a745) | Augustine Ozor |
| 4 | Centralized Security Logging and Alerting | 2026-09-15 | ![Partial](https://img.shields.io/badge/result-Partial-dbab09) | Augustine Ozor |

## 1. Multi-Factor Authentication for Administrative Access

**Test Date:** 2026-09-10 &nbsp;·&nbsp; **Result:** ![Partial](https://img.shields.io/badge/result-Partial-dbab09) &nbsp;·&nbsp; **Tester:** Augustine Ozor

**Procedure / Notes**  
Pulled the full Okta administrator group roster (14 accounts) and cross-referenced each against the MFA factor enrollment export. Confirmed all 14 accounts have MFA enabled, but only 10 of 14 (71%) are enrolled on a hardware security key; the remaining 4 use Okta Verify push. Result marked Partial — the enforcement policy itself is effective, but the factor type does not yet meet the hardware-key standard for all admins.

---

## 2. Encryption of Customer Data at Rest and in Transit

**Test Date:** 2026-09-11 &nbsp;·&nbsp; **Result:** ![Pass](https://img.shields.io/badge/result-Pass-28a745) &nbsp;·&nbsp; **Tester:** Augustine Ozor

**Procedure / Notes**  
Reviewed AWS KMS key policies and encryption settings for all 6 production RDS instances and 3 S3 buckets holding customer data; confirmed AES-256 encryption at rest enabled on all with no exceptions. Checked load balancer TLS configuration and confirmed TLS 1.0/1.1 are disabled, with only TLS 1.2+ ciphers accepted. No gaps found.

---

## 3. Code Change Review and CI/CD Gate Enforcement

**Test Date:** 2026-09-12 &nbsp;·&nbsp; **Result:** ![Pass](https://img.shields.io/badge/result-Pass-28a745) &nbsp;·&nbsp; **Tester:** Augustine Ozor

**Procedure / Notes**  
Sampled 25 merges to the main branch from the last 90 days in GitHub. All 25 required at least one approving review and a passing CI pipeline before merge; no direct pushes or manual overrides were found. Branch protection settings confirmed to technically enforce both requirements.

---

## 4. Centralized Security Logging and Alerting

**Test Date:** 2026-09-15 &nbsp;·&nbsp; **Result:** ![Partial](https://img.shields.io/badge/result-Partial-dbab09) &nbsp;·&nbsp; **Tester:** Augustine Ozor

**Procedure / Notes**  
Reviewed the 30-day alert log and attempted to trace 5 simulated failed-login burst events through the pipeline. 3 of 5 generated an alert within the expected window; 2 were missed due to an alert-threshold misconfiguration. Logging itself is functioning, but alerting reliability does not yet meet the standard needed for a clean pass ahead of the observation period; threshold tuning has been flagged for remediation.

---


---

<div align="center">

[← Evidence](02-evidence.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Findings →](04-findings.md)

</div>
