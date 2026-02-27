---
layout: default
title: Admin Guide
---

# TeamOps Admin Guide

This guide is for HR Administrators who manage TeamOps settings, leave policies, onboarding templates, and employee data. It covers everything from first-time setup to GDPR compliance.

---

## Table of Contents

1. [First-Time Setup](#1-first-time-setup)
2. [Managing the HR Admin Group](#2-managing-the-hr-admin-group)
3. [Configuring Leave Types](#3-configuring-leave-types)
4. [Managing Holidays](#4-managing-holidays)
5. [Setting the Work Week](#5-setting-the-work-week)
6. [Department Mapping](#6-department-mapping)
7. [Onboarding Templates](#7-onboarding-templates)
8. [Starting an Onboarding](#8-starting-an-onboarding)
9. [Monitoring Active Onboardings](#9-monitoring-active-onboardings)
10. [Managing Leave Approvals](#10-managing-leave-approvals)
11. [GDPR: Exporting and Deleting Employee Data](#11-gdpr-exporting-and-deleting-employee-data)
12. [Analytics and Feedback](#12-analytics-and-feedback)
13. [General Settings](#13-general-settings)

---

## 1. First-Time Setup

### What Auto-Initializes

When TeamOps is installed and opened for the first time, it automatically configures itself based on your Jira site's locale:

- **Country detection** -- Identifies your country from the installing user's Jira locale settings.
- **Public holidays** -- Pre-loads the current year's public holidays for your detected country.
- **Default leave types** -- Creates standard leave types: Annual Leave, Sick Leave, and Personal Leave with typical allocations for your country.
- **Work week** -- Sets the default work week (Monday through Friday for most countries).
- **Onboarding templates** -- Makes five built-in templates available: Engineering, Sales, General, HR, and Executive.

### Setup Checklist

Even though TeamOps works out of the box, you should review these settings in your first session:

1. **Verify your country and holidays** -- Go to Settings and confirm the detected country is correct. Add or remove holidays as needed.
2. **Review default leave types** -- Check that the leave types and allocations match your company policy. Add, edit, or remove types as needed.
3. **Set up the HR Admin group** -- Add other HR team members so they also have full admin access.
4. **Map departments** -- Connect your company's departments to Jira users and groups so team availability and reporting work correctly.
5. **Review onboarding templates** -- Look at the built-in templates and customize them to match your onboarding process.
6. **Configure notification preferences** -- Decide which notifications should be active for your organization.

### Accessing Admin Settings

1. Click **Apps** in the top navigation bar.
2. Select **TeamOps HR Portal**.
3. Click the **Settings** gear icon (visible only to HR Admins), or
4. Go to **Jira Administration** > **Apps** > **TeamOps Settings** for the dedicated admin page.

---

## 2. Managing the HR Admin Group

HR Admins have full access to all TeamOps features, including settings, all employee data, analytics, and GDPR tools.

### Adding an HR Admin

1. Open **TeamOps Settings**.
2. Go to the **Access & Roles** section.
3. Under **HR Admins**, click **Add Member**.
4. Search for the Jira user by name or email.
5. Select the user and click **Add**.

### Removing an HR Admin

1. Open **TeamOps Settings** > **Access & Roles**.
2. Find the user in the HR Admins list.
3. Click the **Remove** button next to their name.
4. Confirm the removal.

### Important Notes

- At least one HR Admin must exist at all times. TeamOps will not allow you to remove the last HR Admin.
- The person who installs TeamOps is automatically added as the first HR Admin.
- HR Admin access is separate from Jira's built-in admin roles. A person can be a TeamOps HR Admin without being a Jira site administrator.

---

## 3. Configuring Leave Types

Leave types define the categories of leave your employees can request (e.g., Annual Leave, Sick Leave, Parental Leave).

### Viewing Leave Types

1. Open **TeamOps Settings**.
2. Go to the **Leave Types** section.
3. You will see a table listing all configured leave types with their names, default allocations, and status (active or inactive).

### Adding a New Leave Type

1. Click **Add Leave Type**.
2. Fill in the fields:

| Field | Description | Required? |
|-------|-------------|-----------|
| **Name** | Display name (e.g., "Parental Leave," "Bereavement Leave") | Yes |
| **Default Allocation** | Number of days per year granted to each employee by default | Yes |
| **Description** | Brief explanation shown to employees when they select this type | No |
| **Requires Approval** | Whether requests of this type need manager approval (most do) | Yes |
| **Active** | Whether this type is available for employees to select | Yes |

3. Click **Save**.

### Editing a Leave Type

1. Click the **Edit** button (pencil icon) next to the leave type.
2. Modify any fields.
3. Click **Save**.

Changes apply going forward. Existing approved requests are not affected.

### Deleting a Leave Type

1. Click the **Delete** button (trash icon) next to the leave type.
2. Confirm the deletion.

You cannot delete a leave type that has active (Pending or Approved future) requests. Resolve those requests first, or deactivate the type instead of deleting it.

### Setting Individual Allocations

The default allocation applies to all employees. If a specific employee has a different entitlement (e.g., senior staff with extra vacation days):

1. Go to the employee's profile in TeamOps.
2. Click **Edit Allocations**.
3. Override the allocation for specific leave types.
4. Click **Save**.

---

## 4. Managing Holidays

Holidays are non-working days that are automatically excluded when calculating leave duration. They also appear on the Team Availability calendar.

### Country Selection

1. Open **TeamOps Settings** > **Holidays**.
2. The detected country is shown at the top. To change it, click **Change Country** and select from the dropdown.
3. Public holidays for the selected country are loaded automatically for the current year.

### Reviewing Pre-Loaded Holidays

The holidays table shows:

- **Date** -- The holiday date
- **Name** -- The holiday name (e.g., "New Year's Day," "Christmas Day")
- **Type** -- "Public" for auto-loaded holidays, "Custom" for ones you add manually

Review the list to make sure it is accurate for your organization. Some companies observe holidays that differ from the national calendar.

### Adding a Custom Holiday

1. Click **Add Holiday**.
2. Enter the **Date** and **Name**.
3. Click **Save**.

Use this for company-specific days off (e.g., "Company Founder's Day," "Office Closure Dec 24").

### Removing a Holiday

1. Find the holiday in the list.
2. Click the **Remove** button.
3. Confirm the removal.

You can remove both public and custom holidays. Removed public holidays can be re-added by resetting to the country default.

### Multi-Location Support

If your company has offices in multiple countries, you can add holidays from multiple country calendars. Employees see holidays based on their assigned location (set in their employee profile or department mapping).

---

## 5. Setting the Work Week

The work week defines which days are considered working days. This affects how leave duration is calculated and how the Team Availability calendar displays.

### Configuring Work Days

1. Open **TeamOps Settings** > **Work Week**.
2. You will see all seven days of the week with toggles.
3. Turn **on** the days that are work days for your organization.
4. Turn **off** the days that are rest days.
5. Click **Save**.

The default is Monday through Friday. If your organization works Sunday through Thursday, adjust accordingly.

### How It Affects Leave Calculations

When an employee requests leave from Monday to Sunday in a standard Monday-through-Friday work week:

- Saturday and Sunday are excluded automatically.
- The request counts as 5 business days, not 7.

If a public holiday falls on one of those work days, it is also excluded, reducing the count further.

---

## 6. Department Mapping

Department mapping connects your organizational structure to Jira users. This enables department-based filtering on the Team Availability view and powers the department breakdown in analytics.

### Setting Up Departments

1. Open **TeamOps Settings** > **Departments**.
2. Click **Add Department**.
3. Enter the **Department Name** (e.g., "Engineering," "Marketing," "Finance").
4. Click **Save**.

### Assigning Users to Departments

There are two ways to assign users:

**Option A: Individual assignment**
1. Go to a department.
2. Click **Add Members**.
3. Search for Jira users by name or email.
4. Select users and click **Add**.

**Option B: Map a Jira group**
1. Go to a department.
2. Click **Link Jira Group**.
3. Select an existing Jira group from the dropdown (e.g., "engineering-team").
4. Click **Link**.

All members of that Jira group are automatically included in the department. When users are added to or removed from the Jira group, TeamOps stays in sync.

### Editing and Removing Departments

- To rename a department, click **Edit** next to the department name.
- To remove a department, click **Delete**. This does not delete any user data -- it only removes the grouping.
- To remove a user from a department, click **Remove** next to their name.

---

## 7. Onboarding Templates

Onboarding templates are pre-built checklists that define the tasks a new hire (and supporting teams) need to complete. TeamOps includes five built-in templates that you can use as-is or customize.

### Built-In Templates

| Template | Best For | Example Tasks |
|----------|----------|---------------|
| **General** | Any new hire | Complete tax forms, review employee handbook, set up email, office tour |
| **Engineering** | Developers and technical staff | Set up dev environment, code repository access, architecture walkthrough, first code review |
| **Sales** | Sales and business development | CRM access, product training, shadow calls, meet key accounts |
| **HR** | HR team members | HRIS system access, benefits training, policy review, meet department heads |
| **Executive** | Directors and above | Board introductions, strategy briefing, leadership team meetings, executive tools setup |

### Using a Built-In Template

Built-in templates are ready to use immediately. When you start an onboarding, you select one of these templates and TeamOps creates all the tasks automatically. See [Starting an Onboarding](#8-starting-an-onboarding) for the full process.

### Creating a Custom Template

1. Open **TeamOps Settings** > **Onboarding Templates**.
2. Click **Create Template**.
3. Enter a **Template Name** and **Description**.
4. Select the **Target Role** (who this template is designed for).
5. Add tasks organized by phase:

Each task has:

| Field | Description |
|-------|-------------|
| **Task Name** | Short description of what needs to be done |
| **Description** | Detailed instructions or notes for the person completing the task |
| **Phase** | When the task should be done: "Before Day 1," "First Day," "First Week," "First Month," or "First 90 Days" |
| **Default Assignee Role** | Who typically does this: "New Hire," "Manager," "IT," "HR," or "Custom" |
| **Days Offset** | How many days after the start date this task is due |

6. Click **Save Template**.

### Editing a Template

1. Go to **Onboarding Templates**.
2. Click **Edit** on the template you want to change.
3. Add, remove, or modify tasks.
4. Click **Save**.

Changes to a template do not affect onboardings that are already in progress. They only apply to future onboardings started with that template.

### Duplicating a Template

If you want to create a template similar to an existing one:

1. Click **Duplicate** on the template.
2. A copy is created with "(Copy)" appended to the name.
3. Edit the copy to make your changes.

---

## 8. Starting an Onboarding

When a new employee joins your organization, you start their onboarding in TeamOps to create a structured checklist of tasks.

### Step by Step

1. Open **TeamOps HR Portal** from the Apps menu.
2. Click the **Onboarding** tab.
3. Click **Start New Onboarding**.
4. Fill in the new hire's details:

| Field | Description | Required? |
|-------|-------------|-----------|
| **Employee** | Search for and select the Jira user account for the new hire | Yes |
| **Template** | Select the onboarding template to use | Yes |
| **Start Date** | The employee's first day at the company | Yes |
| **Department** | The department the employee is joining | Yes |
| **Manager** | The employee's direct manager (responsible for manager-assigned tasks) | Yes |
| **Jira Project** | Optionally link to a Jira project (see below) | No |

5. Click **Start Onboarding**.

### Linking a Jira Project

When you link a Jira project to an onboarding:

- TeamOps creates a Jira issue for each onboarding task in that project.
- Task status syncs both ways: completing a task in TeamOps transitions the Jira issue, and transitioning the Jira issue updates the TeamOps checklist.
- Tasks appear on Jira boards and can be tracked alongside regular project work.
- Assignees receive standard Jira notifications for their tasks.

This is optional. If you do not link a project, tasks are tracked entirely within TeamOps.

### What Happens After You Start

1. The onboarding checklist is created based on the selected template.
2. Tasks are assigned to the appropriate people (new hire, manager, IT, HR) based on the template's default assignee roles.
3. Due dates are calculated from the start date using each task's days offset.
4. The new hire and all task assignees receive Jira notifications.
5. The onboarding appears in the **Active Onboardings** list.

---

## 9. Monitoring Active Onboardings

As an HR Admin, you can track the progress of all active onboardings across your organization.

### Viewing Active Onboardings

1. Open **TeamOps HR Portal** > **Onboarding** tab.
2. The **Active Onboardings** section shows all in-progress onboardings.

For each onboarding, you see:

- **Employee name** and department
- **Start date**
- **Template used**
- **Progress bar** showing completion percentage
- **Task counts** (completed / total)
- **Overdue tasks** highlighted in red

### Department View

Use the **Department** filter to see onboardings for a specific department. This is useful when you want to focus on one team's new hires.

### Drilling into an Onboarding

Click on any onboarding to see the full task list:

- Tasks grouped by phase (Before Day 1, First Day, First Week, etc.)
- Status of each task (Not Started, In Progress, Completed, Overdue)
- Assignee for each task
- Linked Jira issue (if applicable -- click to open)

### Taking Action on Overdue Tasks

If tasks are overdue:

1. Identify the overdue tasks (marked in red).
2. Check who is assigned to each task.
3. Reach out to the assignee directly, or reassign the task by clicking **Edit** on the task and selecting a new assignee.
4. TeamOps sends daily reminders for overdue tasks automatically.

### Completing an Onboarding

When all tasks are completed, the onboarding is automatically marked as "Complete." You can also manually mark an onboarding as complete if the remaining tasks are no longer relevant:

1. Open the onboarding.
2. Click **Mark as Complete**.
3. Confirm. Any unfinished tasks are marked as skipped.

---

## 10. Managing Leave Approvals

Leave approval is primarily a Manager responsibility, but HR Admins can also view and manage all leave requests across the organization.

### For Managers: Approving or Rejecting Requests

When an employee on your team submits a leave request, you receive a Jira notification.

1. Click the notification to go to TeamOps, or open **TeamOps HR Portal** > **Leave Requests** tab.
2. Click **Pending Approvals** to see requests waiting for your decision.
3. For each request, you see the employee's name, leave type, dates, duration, and any note they included.
4. Review the request along with the Team Availability calendar to check for scheduling conflicts.
5. Click **Approve** to approve the request, or **Reject** to reject it.
6. If rejecting, add a **comment** explaining why. This comment is visible to the employee.

The employee receives a Jira notification with your decision.

### For HR Admins: Organization-Wide View

As an HR Admin, you can see all leave requests across the entire organization:

1. Go to **Leave Requests** tab.
2. Use the **All Requests** view (available only to HR Admins).
3. Filter by department, status, date range, or leave type.

HR Admins can also override a manager's decision if needed (e.g., approving a request that was incorrectly rejected).

### Best Practices

- **Review requests promptly.** Employees are waiting on your decision, and pending requests affect their visible leave balance.
- **Check the calendar.** Before approving, glance at the Team Availability view to make sure the team has adequate coverage.
- **Be specific when rejecting.** Always add a comment so the employee understands the reason and can resubmit if appropriate.

---

## 11. GDPR: Exporting and Deleting Employee Data

TeamOps is GDPR compliant and provides tools for HR Admins to export or delete individual employee data on request.

### Where Is Data Stored?

All TeamOps data is stored in Atlassian's Forge platform storage, which inherits Atlassian's data residency and security controls. Data never leaves the Atlassian infrastructure.

### Exporting Employee Data

If an employee requests a copy of their data (GDPR "Right of Access"):

1. Open **TeamOps Settings** > **GDPR & Privacy**.
2. Click **Export Employee Data**.
3. Search for and select the employee.
4. Click **Export**.
5. TeamOps generates a downloadable file containing all data stored for that employee, including:
   - Employee profile information
   - Leave request history (all statuses)
   - Leave balances
   - Onboarding task assignments and completion records
6. Download the file and provide it to the employee.

### Deleting Employee Data

If an employee requests data deletion (GDPR "Right to Erasure"), or when an employee leaves the organization:

1. Open **TeamOps Settings** > **GDPR & Privacy**.
2. Click **Delete Employee Data**.
3. Search for and select the employee.
4. Review the summary of what will be deleted.
5. Type the employee's name to confirm.
6. Click **Permanently Delete**.

This action is irreversible. All of the following are permanently removed:

- Employee profile
- All leave requests (past, pending, and future)
- Leave balance records
- Onboarding checklist data and task assignments
- Any associated Jira issue links (the Jira issues themselves remain, but the TeamOps connection is removed)

### Audit Trail

Data exports and deletions are logged in the GDPR audit trail, accessible from the **GDPR & Privacy** settings page. Each entry records who performed the action, when, and for which employee.

---

## 12. Analytics and Feedback

TeamOps provides analytics to help HR Admins understand how the app is being used and identify configuration issues.

### Accessing Analytics

1. Open **TeamOps Settings** > **Analytics**.

### Configuration Insights

The analytics dashboard shows:

- **Leave type usage** -- Which leave types are most and least used. Helps you decide whether to add or remove types.
- **Average approval time** -- How long it takes managers to respond to leave requests. Highlights bottlenecks.
- **Leave trends** -- Monthly and quarterly trends in leave usage across the organization.
- **Onboarding completion rates** -- What percentage of onboardings are completed on time, and which phases have the most overdue tasks.
- **Department breakdown** -- Leave usage and onboarding progress by department.

### Feature Adoption

Track how your team is using TeamOps:

- **Active users** -- How many employees have accessed TeamOps this month.
- **Leave requests submitted** -- Total requests over time.
- **Onboardings started** -- Number of onboardings initiated.
- **Dashboard gadget usage** -- How many users have added the HR Snapshot gadget.

### Using Analytics to Improve

- If approval times are slow, remind managers to check their pending approvals regularly.
- If certain onboarding phases consistently have overdue tasks, review whether the due dates are realistic.
- If a leave type is never used, consider removing it to simplify the employee experience.

---

## 13. General Settings

### Notification Preferences

Control which TeamOps notifications are sent at the organization level:

1. Open **TeamOps Settings** > **Notifications**.
2. Toggle notifications on or off for each event type:
   - Leave request submitted
   - Leave request approved/rejected
   - Leave request cancelled
   - Onboarding task assigned
   - Onboarding task overdue (daily reminder)
   - Onboarding started
3. Click **Save**.

Individual users can further adjust their personal notification preferences through Jira's notification settings.

### Default Leave Allocation Period

Configure whether leave allocations are based on:

- **Calendar year** (January to December)
- **Fiscal year** (set your fiscal year start month)
- **Employee anniversary** (based on each employee's start date)

Go to **TeamOps Settings** > **Leave Policies** to set this.

### Locale Settings

TeamOps auto-detects your locale, but you can override it:

1. Open **TeamOps Settings** > **General**.
2. Change the **Country** (affects holidays and default leave types).
3. Change the **Date Format** (e.g., MM/DD/YYYY vs. DD/MM/YYYY).
4. Click **Save**.

### Data Retention

By default, TeamOps retains all historical data. You can configure automatic archiving of old records:

1. Go to **TeamOps Settings** > **General** > **Data Retention**.
2. Set the retention period for completed onboardings (e.g., archive after 12 months).
3. Leave request history is always retained for compliance purposes unless explicitly deleted via GDPR tools.

---

## Quick Reference: Where to Find Things

| What You Need | Where to Go |
|---------------|-------------|
| All TeamOps settings | Apps > TeamOps HR Portal > Settings gear, or Jira Admin > Apps > TeamOps Settings |
| Add HR Admins | Settings > Access & Roles |
| Configure leave types | Settings > Leave Types |
| Manage holidays | Settings > Holidays |
| Set work week | Settings > Work Week |
| Map departments | Settings > Departments |
| Edit onboarding templates | Settings > Onboarding Templates |
| Start a new onboarding | TeamOps HR Portal > Onboarding > Start New Onboarding |
| View all leave requests | TeamOps HR Portal > Leave Requests > All Requests |
| Export/delete employee data | Settings > GDPR & Privacy |
| View analytics | Settings > Analytics |
| Notification settings | Settings > Notifications |

---

## Need Help?

- **For technical issues or bugs:** Contact TeamOps support through the Atlassian Marketplace listing page.
- **For Jira administration help:** Consult your Jira site administrator.
- **For feature requests:** Submit feedback through the TeamOps Settings > Feedback section or the Marketplace listing.
