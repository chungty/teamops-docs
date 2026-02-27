---
layout: default
title: FAQ
---

# TeamOps Frequently Asked Questions

---

## Setup & Access

### How do I install TeamOps?

TeamOps is installed from the Atlassian Marketplace by a Jira site administrator:

1. Go to [Atlassian Marketplace](https://marketplace.atlassian.com) and search for "TeamOps."
2. Click **Get it now** (or **Try it free** if using a paid tier).
3. Select your Jira site and confirm the installation.
4. Once installed, all users on the site can access TeamOps through **Apps > TeamOps HR Portal** in the top navigation bar.

Only Jira site administrators can install apps. If you are not a site admin, ask your Jira administrator to install it for you.

### What happens on first launch?

TeamOps auto-configures itself the first time it is opened:

- **Country detection:** Identifies your country from your Jira locale.
- **Public holidays:** Loads the current year's public holidays for your country.
- **Default leave types:** Creates Annual Leave, Sick Leave, and Personal Leave with standard allocations.
- **Work week:** Sets Monday through Friday as the default.
- **Onboarding templates:** Makes five built-in templates available (Engineering, Sales, General, HR, Executive).

No manual setup is required to start using the app. Your HR Admin can customize all of these defaults afterward.

### How do I become an HR Admin?

The person who installs TeamOps is automatically the first HR Admin. After that, any existing HR Admin can add others:

1. Open **TeamOps Settings** > **Access & Roles**.
2. Click **Add Member** under HR Admins.
3. Search for the person and add them.

HR Admin access in TeamOps is separate from Jira site administration. You do not need to be a Jira admin to be a TeamOps HR Admin.

### Does TeamOps work with Jira Service Management?

Yes. TeamOps works on both Jira Software and Jira Service Management (JSM). It is installed at the site level and is available to all Jira products on your site. You do not need JSM specifically -- TeamOps works just as well with Jira Software alone.

### Can I use TeamOps with multiple Jira projects?

Yes. When starting an onboarding, you can link it to any Jira project on your site. Different onboardings can be linked to different projects. Leave management is not project-specific -- it works across your entire Jira site.

---

## Leave Management

### How many leave types can I create?

There is no hard limit on the number of leave types. You can create as many as your organization needs (e.g., Annual Leave, Sick Leave, Personal Leave, Parental Leave, Bereavement Leave, Study Leave, Volunteer Day). That said, we recommend keeping the list manageable -- 5 to 10 types covers most organizations. Too many types can confuse employees when submitting requests.

### How are business days calculated?

When you submit a leave request, TeamOps calculates business days by:

1. Counting all days between your start date and end date (inclusive).
2. Subtracting weekend days (or whichever days your HR Admin has configured as non-work days).
3. Subtracting any public or custom holidays that fall within the range.

For example, if you request leave from Monday to Friday in a standard work week, and Wednesday is a public holiday, the request counts as 4 business days.

### Can I cancel a leave request?

Yes. You can cancel a leave request as long as the leave period has not already started:

1. Go to **TeamOps HR Portal** > **Leave Requests**.
2. Find the request in your history.
3. Click **Cancel** and confirm.

If the request was already approved, the days are returned to your available balance. You cannot cancel leave that is currently in progress or in the past.

### Who gets notified when I submit, approve, or reject leave?

| Action | Who Is Notified |
|--------|-----------------|
| Employee submits a request | The employee's manager |
| Manager approves a request | The employee who submitted it |
| Manager rejects a request | The employee who submitted it (with the manager's comment) |
| Employee cancels a request | The employee's manager |

Notifications are delivered through Jira's built-in notification system -- they appear in the Jira notification bell and, depending on settings, by email.

### What happens to my leave balance if my request is rejected?

Nothing. Your balance is only reduced when a request is approved. Pending and rejected requests do not affect your available balance. (Pending requests are shown separately as "Pending" in your balance summary so you know how many days are awaiting a decision.)

### Can a manager see leave balances for their team?

Yes. Managers can view leave balances for their direct reports in the Leave Requests tab. They cannot see balances for employees outside their team. HR Admins can see balances for all employees.

---

## Onboarding

### Can I create my own onboarding templates?

Yes. HR Admins can create custom onboarding templates from scratch or by duplicating and editing one of the five built-in templates (Engineering, Sales, General, HR, Executive). Custom templates let you define your own tasks, phases, assignees, and due date offsets. See the [Admin Guide](admin-guide#7-onboarding-templates) for step-by-step instructions.

### What happens when I link a Jira project to an onboarding?

When you link a Jira project:

- A Jira issue is created for each onboarding task in that project.
- Task status syncs in both directions: completing a task in TeamOps moves the Jira issue to "Done," and transitioning the Jira issue in Jira updates the TeamOps checklist.
- Tasks appear on the project's Jira board and backlog, so they can be tracked alongside regular work.
- Assignees receive standard Jira issue notifications.

Linking a project is optional. Without it, tasks are tracked entirely within TeamOps.

### How do task reminders work?

TeamOps runs a daily check for overdue onboarding tasks. When a task passes its due date without being completed:

- The task is highlighted in red on the onboarding checklist.
- The assigned person receives a Jira notification reminding them the task is overdue.
- The employee's manager and the HR Admin are also notified.
- These reminders repeat daily until the task is completed or the onboarding is marked as finished.

### Can I reassign an onboarding task to someone else?

Yes. HR Admins and Managers can reassign any task in an active onboarding:

1. Open the onboarding and find the task.
2. Click **Edit** on the task.
3. Change the assignee.
4. Click **Save**.

The new assignee receives a notification about the task.

---

## Security & Privacy

### Where is my data stored?

All TeamOps data is stored within Atlassian's Forge platform, which is Atlassian's cloud-native app hosting environment. Your data:

- Lives on Atlassian's infrastructure (AWS), within the same security boundary as Jira itself.
- Inherits Atlassian's data residency controls. If you have configured data residency for your Atlassian site, TeamOps data follows the same rules.
- Never leaves Atlassian's infrastructure. TeamOps does not send data to any third-party servers.
- Is isolated per Jira site. Other organizations cannot access your data.

### Can I export my data?

Yes. There are two types of data export:

- **Individual employee export (GDPR):** HR Admins can export all data for a specific employee, including their profile, leave history, balances, and onboarding records. Go to **TeamOps Settings** > **GDPR & Privacy** > **Export Employee Data**.
- **Analytics data:** The analytics dashboard shows aggregated data about leave usage, onboarding progress, and feature adoption. These can be reviewed on-screen.

### Is TeamOps GDPR compliant?

Yes. TeamOps is designed with GDPR compliance in mind:

- **Right of Access:** HR Admins can export all data stored for any employee.
- **Right to Erasure:** HR Admins can permanently delete all data for an employee.
- **Data Minimization:** TeamOps only stores data necessary for leave management and onboarding (names, dates, leave types, task assignments).
- **Audit Trail:** All data exports and deletions are logged with timestamps and the identity of who performed the action.
- **Data Residency:** Data is stored on Atlassian's Forge platform and follows your site's data residency configuration.

See the [Admin Guide](admin-guide#11-gdpr-exporting-and-deleting-employee-data) for instructions on exporting and deleting data.

### Who can see my leave requests?

- **You** can see all your own requests.
- **Your manager** can see your requests (since they approve them).
- **HR Admins** can see all requests across the organization.
- **Other employees** can see on the Team Availability calendar that you are out, but they cannot see the details of your leave request (such as the leave type or any notes).

---

## Billing & Pricing

### Is there a free tier?

Yes. TeamOps is free for up to 10 users. This includes all features with no restrictions -- leave management, onboarding, templates, the dashboard gadget, GDPR tools, and analytics. If your organization has 10 or fewer people using Jira, you can use TeamOps at no cost indefinitely.

### How does per-user pricing work?

Pricing is based on the number of Jira users on your site (not just the number who actively use TeamOps):

| Tier | Users | Price |
|------|-------|-------|
| Free | 1-10 | $0/month |
| Standard | 11-100 | $3 per user/month |
| Growth | 101-500 | $2 per user/month |

Billing is handled through the Atlassian Marketplace. Your Jira site administrator manages the subscription from **Jira Administration** > **Manage Apps**.

### Do I get charged during the evaluation period?

No. Atlassian Marketplace apps typically include a free evaluation period (usually 30 days) during which you can try the full app without being charged. After the evaluation ends, you can choose to subscribe or uninstall.

### What happens if I exceed 10 users?

If your Jira site grows beyond 10 users, TeamOps will prompt your Jira administrator to upgrade to the Standard tier. The app continues to work during a grace period so there is no disruption. Once the subscription is activated, billing begins for all users on the site.

---

## Troubleshooting

### TeamOps is not showing up in the Apps menu

- Make sure the app has been installed by your Jira site administrator.
- Try refreshing your browser or clearing your cache.
- Check that you have permission to access apps on your Jira site (some sites restrict app visibility).

### My country's holidays are incorrect or missing

Your HR Admin can fix this:

1. Go to **TeamOps Settings** > **Holidays**.
2. Verify the correct country is selected.
3. Add, remove, or edit individual holidays as needed.

If the auto-detected country is wrong, the HR Admin can change it from the Holidays settings page.

### I submitted a leave request but my manager did not receive a notification

- Ask your manager to check their Jira notification bell -- notifications may be there but not sent by email.
- Confirm that your manager is set as your manager in TeamOps (your HR Admin can verify this in department mapping).
- Check that leave notifications are enabled in **TeamOps Settings** > **Notifications**.
- Verify your manager's Jira notification preferences allow email delivery.

### My leave balance looks wrong

- Remember that pending requests reduce your displayed "Available" balance even though they have not been approved yet.
- If your HR Admin recently changed your allocation, the balance updates immediately.
- Check your leave history for any requests you may have forgotten about.
- Contact your HR Admin if the numbers still do not match your expectation.

---

## Still Have Questions?

- **Check the [User Guide](user-guide)** for step-by-step instructions on common tasks.
- **Check the [Admin Guide](admin-guide)** for configuration and setup help.
- **Contact your HR Admin** for questions about your organization's leave policies or onboarding process.
- **Contact TeamOps support** through the Atlassian Marketplace listing for bug reports or technical issues.
