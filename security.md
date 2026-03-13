---
layout: default
title: Security Policy
---

# TeamOps Security Policy

**Effective Date:** March 13, 2026
**Publisher:** PPLX Software

---

## Architecture

TeamOps is a Forge-native Jira application. It runs entirely on Atlassian's infrastructure with no external servers, databases, or network calls.

- **Runtime:** Atlassian Forge (sandboxed execution environment)
- **Data Storage:** Forge Custom Entity Store (Atlassian-managed)
- **Authentication:** Atlassian OAuth 2.0 (platform-managed)
- **External Network Calls:** None — zero external fetch declarations in the app manifest

---

## Data Protection

| Layer | Protection |
|---|---|
| **Encryption at Rest** | AES-256, managed by Atlassian Forge platform |
| **Encryption in Transit** | TLS 1.2+, all communication within Atlassian infrastructure |
| **Data Residency** | Follows your Atlassian tenant's configured region (EU, US, AU, etc.) |
| **Access Control** | Role-based (HR Admin, Manager, Employee), enforced on every API call |
| **PII in Logs** | None — logs reference entity IDs and account IDs only |
| **Cookies / Tracking** | None |

---

## Access Control

TeamOps enforces role-based access control (RBAC) on every server-side resolver call:

| Role | Access Scope |
|---|---|
| **HR Admin** | Full read/write access to all employee data, configuration, export, and erasure |
| **Manager** | Read/write access to their direct team's leave requests and onboarding progress |
| **Employee** | Read/write access to their own data only |

Roles are assigned via Atlassian group membership. PPLX Software personnel have no access to customer data — the Forge platform does not provide app publishers with access to tenant data.

---

## Vulnerability Management

- **Static Analysis:** `forge lint` is run before every deployment
- **Dependency Scanning:** `npm audit` is run as part of the development workflow
- **Dependencies:** Version-locked via `package-lock.json`, regularly updated
- **Secrets Management:** All sensitive values stored in Forge encrypted environment variables — never in source code

---

## Reporting a Security Vulnerability

If you discover a security vulnerability in TeamOps, please report it responsibly:

**Email:** [pplx.teamops@gmail.com](mailto:pplx.teamops@gmail.com)

Please include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact

We will acknowledge your report within 48 hours and provide an initial assessment within 5 business days.

---

## Incident Response

1. **Detection and Triage** — Assess severity and scope within 24 hours
2. **Containment** — For critical vulnerabilities, submit a patched version to the Atlassian Marketplace immediately
3. **Notification** — Notify affected customers through the Marketplace listing and direct communication
4. **Remediation** — Perform root cause analysis and implement preventive measures
5. **Disclosure** — Disclose material issues responsibly with appropriate timelines

---

## Compliance

TeamOps supports GDPR compliance through built-in features:

- **Data Export:** HR Admins can export all data for any employee
- **Data Erasure:** HR Admins can permanently delete all data for any employee (right to be forgotten)
- **Data Minimization:** Only data necessary for leave management and onboarding is collected
- **No Third-Party Sharing:** Zero external data egress

The Forge platform operates under Atlassian's SOC 2 Type II and ISO 27001 certifications, which cover the infrastructure, compute environment, and data storage layer used by TeamOps.

---

## Contact

**PPLX Software**
Email: [pplx.teamops@gmail.com](mailto:pplx.teamops@gmail.com)
Address: PPLX Software, 5432 Geary Blvd, Unit #898, San Francisco, CA 94121, USA

For platform-level security questions, refer to [Atlassian's Trust Center](https://www.atlassian.com/trust).
