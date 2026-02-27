---
layout: default
title: Privacy Policy
---

# TeamOps Privacy Policy

**Effective Date:** February 24, 2026
**Last Updated:** February 24, 2026
**Publisher:** PPLX Software

---

## 1. Introduction

TeamOps is a Forge-native Jira application that provides integrated leave management and employee onboarding capabilities directly within Atlassian Jira. The app runs entirely on Atlassian's infrastructure and carries the "Runs on Atlassian" trust badge.

**Data Controller:** The organization that installs TeamOps on their Atlassian site is the data controller. PPLX Software, as the app publisher, acts as a data processor on behalf of the installing organization.

This Privacy Policy explains what data TeamOps collects, how it is stored, who can access it, and what rights you have regarding your data.

---

## 2. Data We Collect

TeamOps collects and stores the following categories of personal data:

| Data Category | Specific Fields | Purpose |
|---|---|---|
| **Employee Identity** | Full name, email address | Identify employees within leave and onboarding workflows |
| **Leave Records** | Leave dates, leave type (e.g., annual, sick, personal), leave status, approval history | Process and track leave requests |
| **Onboarding Data** | Task assignments, completion status, onboarding checklist progress, department assignment | Manage employee onboarding workflows |
| **Role Assignments** | RBAC role (HR Admin, Manager, Employee), team/group membership | Enforce access control within the app |

TeamOps does **not** collect:
- Financial or banking information
- Government-issued identification numbers
- Health or medical records beyond leave type categorization
- Biometric data
- Location or geolocation data
- Browser fingerprints or device identifiers

---

## 3. How We Collect Data

All data is collected exclusively through direct user input within the Jira interface. Specifically:

- **Employee-initiated:** Employees submit leave requests and update onboarding tasks through Jira UI panels and forms.
- **Manager/HR-initiated:** Managers approve or deny leave requests. HR Admins configure onboarding templates, assign tasks, and manage employee records.
- **Atlassian platform data:** TeamOps reads user identity information (name, email, account ID) from the Atlassian user profile via authorized Jira API scopes.

TeamOps makes **zero external network calls**. No data is collected from third-party sources, external APIs, advertising networks, or analytics services.

---

## 4. Where Data Is Stored

All application data is stored in the **Forge Custom Entity Store**, which is part of Atlassian's Forge platform infrastructure.

Key storage characteristics:

- **Data Residency:** Data follows the Atlassian tenant's configured data residency region. If your Atlassian site is pinned to a specific region (e.g., EU, US, AU), TeamOps data resides in that same region.
- **Infrastructure:** Atlassian manages the underlying infrastructure, including physical security, network security, and platform-level encryption.
- **No External Storage:** TeamOps does not transmit or replicate data to any external databases, cloud services, or third-party storage systems.
- **No Local Storage:** TeamOps does not store data in browser local storage, session storage, or cookies.

---

## 5. Who Can Access Data

TeamOps enforces role-based access control (RBAC) with three roles, validated on every API resolver call:

| Role | Data Access Scope |
|---|---|
| **HR Admin** | Full read/write access to all employee leave records, onboarding data, and app configuration. Can export and delete employee data. |
| **Manager** | Read/write access to leave requests and onboarding progress for employees within their assigned team only. |
| **Employee** | Read/write access to their own leave requests and onboarding tasks only. No access to other employees' data. |

Role assignments are managed through Atlassian group membership. Every data request is checked against the requesting user's role before data is returned.

PPLX Software personnel do **not** have access to customer data stored within TeamOps. The Forge platform does not provide app publishers with access to tenant data.

---

## 6. Data Retention

- **Active Use:** Data persists in the Forge Custom Entity Store for as long as the app remains installed on the Atlassian site.
- **HR Admin Deletion:** HR Admins can delete individual employee records at any time through the app's built-in data management features, including the GDPR data erasure function.
- **App Uninstallation:** When TeamOps is uninstalled from an Atlassian site, all data stored in the Forge Custom Entity Store for that tenant is deleted by the Atlassian platform in accordance with Atlassian's data retention policies.
- **No Backups by Publisher:** PPLX Software does not maintain separate backups or copies of customer data. All data lifecycle management is handled by the Forge platform.

---

## 7. Your Rights

TeamOps is designed with data subject rights built directly into the application:

### Right of Access
Employees can view all of their own leave records and onboarding data through the app interface at any time. HR Admins can generate a complete data export for any employee.

### Right to Data Portability (Export)
The app includes a **data export** feature that produces a structured export of all data associated with a specific employee. This can be initiated by HR Admins to fulfill data access requests.

### Right to Erasure (Right to Be Forgotten)
The app includes a **right-to-erasure** feature that permanently deletes all data associated with a specific employee from the Forge Custom Entity Store. This can be initiated by HR Admins to fulfill deletion requests.

### Right to Rectification
Employees can update their own leave requests (where workflow rules permit). HR Admins can modify any employee record.

### How to Exercise Your Rights
Contact your organization's HR administrator to initiate a data export or erasure request through the TeamOps interface. For questions directed to the app publisher, see the Contact Information section below.

---

## 8. Third-Party Data Sharing

**TeamOps shares no data with any third party.**

- The app makes **zero external network calls**. There are no external fetch declarations in the app manifest.
- No data is sent to analytics services, advertising platforms, error tracking services, or any external API.
- No data is shared with PPLX Software or any affiliated entity.
- The only data transmission occurs between the Forge app runtime and the Forge Custom Entity Store, both of which operate entirely within Atlassian's infrastructure.

---

## 9. Cookies and Tracking

**TeamOps uses no cookies and performs no tracking.**

- The app runs as a Forge UI Kit application within the Jira interface. It does not set, read, or rely on browser cookies.
- No analytics scripts, tracking pixels, or fingerprinting techniques are used.
- No session tokens are managed by the app; authentication is handled entirely by the Atlassian platform.

---

## 10. Security

### Platform Security
TeamOps runs on Atlassian's Forge platform, which provides:

- **Encryption at Rest:** All data in the Forge Custom Entity Store is encrypted at rest using AES-256 encryption.
- **Encryption in Transit:** All communication between Forge components uses TLS 1.2 or higher.
- **Platform Certifications:** The Atlassian Forge platform operates under Atlassian's SOC 2 Type II and ISO 27001 certifications.
- **Sandboxed Execution:** Forge apps run in isolated sandboxes with no direct access to the underlying infrastructure.

### Application Security
- **No Hardcoded Secrets:** All sensitive configuration values are managed through Forge encrypted environment variables (`forge variables set`), never stored in source code.
- **No PII in Logs:** The application is designed to exclude personally identifiable information from all log output.
- **No Vulnerable Dependencies:** Dependencies are regularly scanned for known vulnerabilities.
- **Input Validation:** All user inputs are validated before processing.
- **RBAC Enforcement:** Access control checks are performed on every resolver call, not just at the UI layer.

---

## 11. Changes to This Policy

We may update this Privacy Policy to reflect changes in the app's functionality, legal requirements, or industry best practices. When we make material changes:

- The "Last Updated" date at the top of this policy will be revised.
- A notice will be included in the app's release notes on the Atlassian Marketplace.
- For significant changes affecting data collection or sharing, we will provide advance notice through the Marketplace listing.

We encourage you to review this policy periodically.

---

## 12. Contact Information

For questions, concerns, or requests related to this Privacy Policy or your personal data:

**PPLX Software**
Email: pplx.teamops@gmail.com
Address: PPLX Software, 5432 Geary Blvd, Unit #898, San Francisco, CA 94121, USA

For data export or erasure requests, please contact your organization's HR administrator, who can initiate these actions directly within the TeamOps application.

For issues related to the Atlassian platform infrastructure, refer to [Atlassian's Privacy Policy](https://www.atlassian.com/legal/privacy-policy) and [Atlassian's Trust Center](https://www.atlassian.com/trust).
