# 🐞 Findings

> 2 findings raised from control testing — only the gaps testing actually surfaced, not a padded list.

| # | Title | Severity | Status | Source | Due Date |
|---|---|---|---|---|---|
| 1 | Incomplete Hardware Key Enrollment for Administrator MFA | ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | Self-Assessment | 2026-10-31 |
| 2 | Alert Threshold Misconfiguration Causing Missed Security Alerts | ![High](https://img.shields.io/badge/severity-High-e36209) | ![In Remediation](https://img.shields.io/badge/status-In%20Remediation-fb8c00) | Self-Assessment | 2026-10-15 |

## 1. Incomplete Hardware Key Enrollment for Administrator MFA

**Severity:** ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49) &nbsp;·&nbsp; **Source:** Self-Assessment  
**Related Control:** CTL-mus4evbf — Multi-Factor Authentication for Administrative Access  
**Owner:** IT Security Team &nbsp;·&nbsp; **Due Date:** 2026-10-31

**Description**  
Control testing on 2026-09-10 found that only 10 of 14 (71%) administrator accounts are enrolled on a hardware security key as required; the remaining 4 accounts authenticate with Okta Verify push, a weaker factor than the control's target design. MFA itself is enforced for all 14 accounts, so the gap is in factor strength, not coverage.

**Recommendation**  
Complete hardware key enrollment for the remaining 4 administrator accounts. Update the Okta sign-on policy for the Administrators group to require a hardware key factor specifically (not just 'any MFA factor'), so push-only enrollment is no longer accepted for privileged access going forward.

---

## 2. Alert Threshold Misconfiguration Causing Missed Security Alerts

**Severity:** ![High](https://img.shields.io/badge/severity-High-e36209) &nbsp;·&nbsp; **Status:** ![In Remediation](https://img.shields.io/badge/status-In%20Remediation-fb8c00) &nbsp;·&nbsp; **Source:** Self-Assessment  
**Related Control:** CTL-mus4jo8z — Centralized Security Logging and Alerting  
**Owner:** Security Operations &nbsp;·&nbsp; **Due Date:** 2026-10-15

**Description**  
Control testing on 2026-09-15 simulated 5 failed-login burst events to validate the security monitoring pipeline; only 3 of 5 generated an alert within the expected window. Root cause identified as a misconfigured alert threshold that fails to trigger on lower-volume burst patterns, creating a detection gap for this type of event.

**Recommendation**  
Adjust the failed-login burst alert threshold to trigger on the volume pattern missed during testing. Re-run the 5-event simulation to confirm 5 of 5 detection before the SOC 2 observation period begins, and retain the updated configuration and re-test results as evidence.

---


---

<div align="center">

[← Control Tests](03-control-tests.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Tasks →](05-tasks.md)

</div>
