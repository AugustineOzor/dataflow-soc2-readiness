# 📎 Evidence

> 5 evidence artifacts collected to support control testing, organized by the control each one backs.

| # | Title | Type | Related Control | Owner |
|---|---|---|---|---|
| 1 | Okta Admin Console — MFA Enforcement Policy Screenshot | Screenshot | CTL-mus2w4pr — Multi-Factor Authentication for Administrative Access | IT Security Team |
| 2 | Okta Admin Factor Enrollment Export (Hardware Key Status) | Export | CTL-mus2w4pr — Multi-Factor Authentication for Administrative Access | IT Security Team |
| 3 | AWS KMS Encryption Configuration — Production Data Stores | Configuration | CTL-mus2yaob — Encryption of Customer Data at Rest and in Transit | Engineering Team |
| 4 | GitHub Branch Protection Rules — main Branch | Screenshot | CTL-mus2z64j — Code Change Review and CI/CD Gate Enforcement | DevOps Lead |
| 5 | Security Monitoring Platform Alert Log — Last 30 Days | Log | CTL-mus32k7f — Centralized Security Logging and Alerting | Security Operations |

## 1. Okta Admin Console — MFA Enforcement Policy Screenshot

**Type:** Screenshot &nbsp;·&nbsp; **Owner:** IT Security Team  
**Related Control:** CTL-mus2w4pr — Multi-Factor Authentication for Administrative Access  
**Location:** `Evidence Repository / SOC2 / CC6.1 / okta-mfa-policy-screenshot.png`

**Notes**  
Shows the Okta sign-on policy requiring a second factor for every account in the Administrators group; confirms the policy is active and applied org-wide, not just to a test group.

---

## 2. Okta Admin Factor Enrollment Export (Hardware Key Status)

**Type:** Export &nbsp;·&nbsp; **Owner:** IT Security Team  
**Related Control:** CTL-mus2w4pr — Multi-Factor Authentication for Administrative Access  
**Location:** `Evidence Repository / SOC2 / CC6.1 / okta-admin-factor-enrollment-export.csv`

**Notes**  
CSV export from Okta listing each administrator account and its enrolled MFA factor type; shows 70% enrolled on hardware security keys and the remainder on Okta Verify push — supports the Partially Effective rating on this control.

---

## 3. AWS KMS Encryption Configuration — Production Data Stores

**Type:** Configuration &nbsp;·&nbsp; **Owner:** Engineering Team  
**Related Control:** CTL-mus2yaob — Encryption of Customer Data at Rest and in Transit  
**Location:** `Evidence Repository / SOC2 / CC6.7 / aws-kms-encryption-config.json`

**Notes**  
Exported AWS KMS key policy and RDS/S3 encryption settings for all production data stores; confirms AES-256 encryption at rest is enabled by default with no unencrypted resources found.

---

## 4. GitHub Branch Protection Rules — main Branch

**Type:** Screenshot &nbsp;·&nbsp; **Owner:** DevOps Lead  
**Related Control:** CTL-mus2z64j — Code Change Review and CI/CD Gate Enforcement  
**Location:** `Evidence Repository / SOC2 / CC8.1 / github-branch-protection-main.png`

**Notes**  
Screenshot of the repository settings page showing required status checks (CI pipeline) and at least one required approving review before merge to main, with force-push and direct-push disabled.

---

## 5. Security Monitoring Platform Alert Log — Last 30 Days

**Type:** Log &nbsp;·&nbsp; **Owner:** Security Operations  
**Related Control:** CTL-mus32k7f — Centralized Security Logging and Alerting  
**Location:** `Evidence Repository / SOC2 / CC7.2 / security-monitoring-alert-log-30d.csv`

**Notes**  
Raw export of triggered alerts (failed logins, anomalous admin activity) over the last 30 days; being used to begin validating alert accuracy and response times ahead of the SOC 2 observation period, consistent with the control's current Not Tested rating.

---


---

<div align="center">

[← Controls](01-controls.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Control Tests →](03-control-tests.md)

</div>
