# 📋 Tasks

> 4 remediation tasks tracking each finding to closure, sequenced rather than bundled.

| # | Task | Priority | Status | Assignee | Due Date |
|---|---|---|---|---|---|
| 1 | Enroll remaining admin accounts on hardware security keys | ![Medium](https://img.shields.io/badge/priority-Medium-dbab09) | ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) | IT Security Team | 2026-10-20 |
| 2 | Update Okta MFA policy to require hardware key for Administrators group | ![Medium](https://img.shields.io/badge/priority-Medium-dbab09) | ![Not Started](https://img.shields.io/badge/status-Not%20Started-6a737d) | IT Security Team | 2026-10-31 |
| 3 | Fix failed-login burst alert threshold configuration | ![High](https://img.shields.io/badge/priority-High-e36209) | ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) | Security Operations | 2026-10-08 |
| 4 | Re-run alert simulation to confirm 5/5 detection and document evidence | ![High](https://img.shields.io/badge/priority-High-e36209) | ![Not Started](https://img.shields.io/badge/status-Not%20Started-6a737d) | Security Operations | 2026-10-15 |

## 1. Enroll remaining admin accounts on hardware security keys

**Priority:** ![Medium](https://img.shields.io/badge/priority-Medium-dbab09) &nbsp;·&nbsp; **Status:** ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09)  
**Assignee:** IT Security Team &nbsp;·&nbsp; **Due Date:** 2026-10-20

**Description / Notes**  
4 of 14 administrator accounts are still enrolled on Okta Verify push instead of a hardware security key (per 2026-09-10 control test). Enroll the remaining 4 accounts so all 14 are on hardware keys. Remediates finding: Incomplete Hardware Key Enrollment for Administrator MFA.

---

## 2. Update Okta MFA policy to require hardware key for Administrators group

**Priority:** ![Medium](https://img.shields.io/badge/priority-Medium-dbab09) &nbsp;·&nbsp; **Status:** ![Not Started](https://img.shields.io/badge/status-Not%20Started-6a737d)  
**Assignee:** IT Security Team &nbsp;·&nbsp; **Due Date:** 2026-10-31

**Description / Notes**  
Once all administrator accounts are enrolled on hardware keys, update the Okta sign-on policy for the Administrators group to require a hardware key factor specifically, so push-only MFA no longer satisfies the policy going forward. Depends on completion of the enrollment task above.

---

## 3. Fix failed-login burst alert threshold configuration

**Priority:** ![High](https://img.shields.io/badge/priority-High-e36209) &nbsp;·&nbsp; **Status:** ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09)  
**Assignee:** Security Operations &nbsp;·&nbsp; **Due Date:** 2026-10-08

**Description / Notes**  
Root cause of missed alerts in the 2026-09-15 control test: alert threshold does not trigger on lower-volume failed-login burst patterns. Adjust the threshold configuration in the security monitoring platform to close this detection gap. Remediates finding: Alert Threshold Misconfiguration Causing Missed Security Alerts.

---

## 4. Re-run alert simulation to confirm 5/5 detection and document evidence

**Priority:** ![High](https://img.shields.io/badge/priority-High-e36209) &nbsp;·&nbsp; **Status:** ![Not Started](https://img.shields.io/badge/status-Not%20Started-6a737d)  
**Assignee:** Security Operations &nbsp;·&nbsp; **Due Date:** 2026-10-15

**Description / Notes**  
After the alert threshold fix is deployed, re-run the same 5 simulated failed-login burst events used in the original test. Confirm all 5 generate an alert within the expected window, and save the updated configuration plus re-test results as evidence ahead of the SOC 2 observation period. Depends on completion of the threshold fix task above.

---


---

<div align="center">

[← Findings](04-findings.md) &nbsp;|&nbsp; [🏠 Home](README.md)

</div>
