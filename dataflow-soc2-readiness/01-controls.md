# 🛡️ Controls

> 4 controls implemented and tested against SOC 2 Trust Services Criteria ahead of DataFlow Analytics' Type II observation period.

| # | Control | Framework | Reference | Effectiveness | Frequency |
|---|---|---|---|---|---|
| 1 | Multi-Factor Authentication for Administrative Access | SOC 2 | `CC6.1` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 2 | Encryption of Customer Data at Rest and in Transit | SOC 2 | `CC6.7` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Continuous |
| 3 | Code Change Review and CI/CD Gate Enforcement | SOC 2 | `CC8.1` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Continuous |
| 4 | Centralized Security Logging and Alerting | SOC 2 | `CC7.2` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Continuous |

## 1. Multi-Factor Authentication for Administrative Access

**Framework:** SOC 2 `CC6.1` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** IT Security Team

**Description**  
Enforce MFA on all administrative and production environment accounts using Okta, with hardware security keys (YubiKey) required for access to production AWS, the data warehouse, and the customer BI platform admin console. Enforced via Okta sign-on policies that block authentication without a verified second factor.

**Decision Rationale**  
Rated Partially Effective because Okta sign-on policies currently enforce MFA for all admin accounts, but hardware key enrollment is only complete for 70% of administrators — the remainder still authenticate with Okta Verify push, a weaker factor than the target control design. Full hardware key rollout is targeted for completion before the SOC 2 observation period begins.

---

## 2. Encryption of Customer Data at Rest and in Transit

**Framework:** SOC 2 `CC6.7` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** Engineering Team

**Description**  
All customer data stored in the production database and data warehouse is encrypted at rest using AES-256, with keys managed through AWS KMS. All data in transit between the application, APIs, and client browsers is encrypted using TLS 1.2 or higher, enforced at the load balancer with TLS 1.0/1.1 disabled.

**Decision Rationale**  
Rated Effective because AWS KMS encryption-at-rest is enabled by default across all production data stores with no exceptions found in the latest configuration review, and load balancer configuration confirms TLS 1.0/1.1 are disabled, leaving no unencrypted transmission path for customer data.

---

## 3. Code Change Review and CI/CD Gate Enforcement

**Framework:** SOC 2 `CC8.1` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** DevOps Lead

**Description**  
All production code changes require at least one peer review approval and must pass automated CI/CD checks (unit tests, static code analysis, dependency vulnerability scan) before merge to the main branch, enforced through GitHub branch protection rules that block merges without these checks passing.

**Decision Rationale**  
Rated Effective because GitHub branch protection settings were reviewed and confirmed to technically block any merge to main without a passing CI pipeline and at least one approving review, and a sample of the last 90 days of merges showed no exceptions or manual overrides.

---

## 4. Centralized Security Logging and Alerting

**Framework:** SOC 2 `CC7.2` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** Security Operations

**Description**  
Security-relevant events (authentication attempts, admin actions, API access anomalies, infrastructure changes) are centralized in the security monitoring platform, with automated alerts configured for anomalous admin activity and failed-login thresholds, routed to the on-call security engineer.

**Decision Rationale**  
Rated Not Tested because the centralized logging and alerting pipeline was only recently implemented and has not yet run through a full observation period; alert accuracy, response times, and false-positive rates have not been validated against real incidents, so effectiveness cannot be confirmed ahead of the SOC 2 Type II audit window.

---


---

<div align="center">

[← Overview](README.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Evidence →](02-evidence.md)

</div>
