---
layout: default
title: User Guide
---

# TeamOps User Guide

Welcome to TeamOps -- the leave management and employee onboarding app for Jira. This guide is for employees, managers, and anyone using TeamOps day-to-day.

---

## Table of Contents

1. [Getting Started](#1-getting-started)
2. [Checking Team Availability](#2-checking-team-availability)
3. [Submitting a Leave Request](#3-submitting-a-leave-request)
4. [Viewing Your Leave Balance](#4-viewing-your-leave-balance)
5. [Cancelling a Leave Request](#5-cancelling-a-leave-request)
6. [Your Onboarding Checklist](#6-your-onboarding-checklist)
7. [Jira Notifications](#7-jira-notifications)
8. [Dashboard Gadget](#8-dashboard-gadget)

---

## 1. Getting Started

### Where to Find TeamOps

Once your Jira administrator has installed TeamOps from the Atlassian Marketplace, you can access it in two ways:

- **Global navigation:** Click **Apps** in the top navigation bar, then select **TeamOps HR Portal**. This opens the main TeamOps interface with three tabs: Team Availability, Leave Requests, and Onboarding.
- **Project page (Onboarding):** If your HR Admin has linked onboarding to a Jira project, you will also see an **Onboarding** tab on that project's left sidebar.

### First-Time Experience

The first time you open TeamOps, the app automatically:

- Detects your locale (country and language) from your Jira profile
- Shows public holidays for your country
- Displays your available leave types and balances

No setup is needed on your part. If anything looks incorrect (wrong country, missing leave types), contact your HR Admin.

### Understanding Your Role

TeamOps has three roles:

| Role | What You Can Do |
|------|----------------|
| **Employee** | View team availability, submit and cancel your own leave requests, complete your onboarding checklist, view your leave balance |
| **Manager** | Everything an Employee can do, plus approve or reject leave requests for your direct reports, and monitor onboarding progress for your team |
| **HR Admin** | Full access to all settings, all employee data, templates, analytics, and GDPR tools |

Your role is determined by your HR Admin. If you manage direct reports in TeamOps, you automatically get Manager capabilities for those people.

---

## 2. Checking Team Availability

The **Team Availability** tab is the first thing you see when you open TeamOps. It answers the question: "Who is available on my team today?"

### Views

You can switch between three views using the toggle at the top:

- **Today** -- Shows who is out right now. Names are listed with their leave type (e.g., "Annual Leave" or "Sick Leave").
- **Week** -- Shows a 5-day view (Monday through Friday, or your configured work week) with colored bars indicating who is out and when.
- **Month** -- Shows a full calendar month. Each day shows an indicator for team members who are on leave.

### Filtering by Department

If your organization has multiple departments, use the **Department** dropdown to filter the view:

1. Click the **Department** dropdown above the calendar.
2. Select one or more departments (e.g., "Engineering," "Marketing").
3. The view updates to show only people in those departments.

To clear the filter, select **All Departments**.

### What the Colors Mean

- **Blue** -- Approved leave (the person is confirmed to be out)
- **Yellow/Orange** -- Pending leave request (awaiting manager approval)
- **Gray** -- Public holiday (the whole team is off)

---

## 3. Submitting a Leave Request

### Step by Step

1. Open **TeamOps HR Portal** from the Apps menu.
2. Click the **Leave Requests** tab.
3. Click the **Request Leave** button.
4. Fill in the form (see field descriptions below).
5. Click **Submit**.

Your request is sent to your manager for approval. You will receive a Jira notification when it is approved or rejected.

### Field Descriptions

| Field | Description | Required? |
|-------|-------------|-----------|
| **Leave Type** | Select from the available types (e.g., Annual Leave, Sick Leave, Personal Leave). Your HR Admin configures which types are available. | Yes |
| **Start Date** | The first day of your leave. Click the date picker to select. | Yes |
| **End Date** | The last day of your leave. For a single day off, set this to the same date as the Start Date. | Yes |
| **Note** | Optional message to your manager explaining the reason. For sick leave, your organization may require a note. | No |

### How Business Days Are Calculated

TeamOps automatically calculates the number of business days for your request. It excludes:

- Weekends (or your organization's configured non-work days)
- Public holidays for your country

For example, if you request Monday through Friday of a week that includes a Wednesday public holiday, TeamOps counts 4 business days, not 5.

### Request Statuses

After you submit, your request goes through these statuses:

| Status | Meaning |
|--------|---------|
| **Pending** | Submitted and waiting for your manager to review |
| **Approved** | Your manager approved the request. The days are deducted from your balance. |
| **Rejected** | Your manager rejected the request. You will see their comment explaining why. |
| **Cancelled** | You cancelled the request before or after approval. |

---

## 4. Viewing Your Leave Balance

### Where to Find It

1. Open **TeamOps HR Portal** from the Apps menu.
2. Click the **Leave Requests** tab.
3. Your leave balance is displayed at the top of the page in summary cards.

### What You Will See

Each leave type shows:

- **Total Allocation** -- The number of days you are entitled to for the current year (set by your HR Admin).
- **Used** -- Days you have already taken (approved and past).
- **Pending** -- Days in pending requests that have not been approved yet.
- **Available** -- Days remaining. This is calculated as: Total - Used - Pending.

### Leave History

Below the balance summary, you will see a table of all your leave requests for the current year, including:

- Leave type
- Dates
- Number of days
- Status (Pending, Approved, Rejected, or Cancelled)
- Any comments from your manager

---

## 5. Cancelling a Leave Request

You can cancel a leave request that is **Pending** or **Approved**, as long as the leave has not already started.

### How to Cancel

1. Open **TeamOps HR Portal** and go to the **Leave Requests** tab.
2. Find the request you want to cancel in your leave history.
3. Click the **Cancel** button on that row.
4. Confirm the cancellation when prompted.

### What Happens After Cancellation

- If the request was **Approved**, the days are added back to your available balance.
- If the request was **Pending**, it is simply removed from the approval queue.
- Your manager receives a notification that you cancelled the request.
- The request remains visible in your history with a "Cancelled" status.

### Restrictions

- You cannot cancel a request for leave that has already started or is in the past.
- If you need to modify dates on an approved request, cancel it and submit a new one.

---

## 6. Your Onboarding Checklist

If you are a new hire, your HR Admin may set up an onboarding checklist for you in TeamOps. This checklist guides you through everything you need to do in your first days and weeks.

### Viewing Your Checklist

1. Open **TeamOps HR Portal** from the Apps menu.
2. Click the **Onboarding** tab.
3. You will see your onboarding checklist organized by phases (e.g., "Before Day 1," "First Day," "First Week," "First Month").

If your onboarding is linked to a Jira project, you can also access it from that project's sidebar under **Onboarding**.

### Completing Tasks

Each task in your checklist has:

- **Task name** -- What you need to do (e.g., "Complete tax forms," "Set up development environment").
- **Description** -- Detailed instructions for the task.
- **Assignee** -- Who is responsible. Some tasks are assigned to you; others may be assigned to IT, your manager, or HR.
- **Due date** -- When the task should be completed.
- **Jira issue link** -- If linked to a Jira project, clicking the task opens the corresponding Jira issue.

To mark a task as complete:

1. Click the **checkbox** next to the task, or
2. If it is linked to a Jira issue, transition the issue to "Done" in Jira -- TeamOps syncs the status automatically.

### Tracking Your Progress

A progress bar at the top of your onboarding page shows:

- How many tasks you have completed out of the total
- Your overall completion percentage
- Which phase you are currently in

### Overdue Tasks

If a task passes its due date without being completed, it is highlighted in red. Your manager and HR Admin can see overdue tasks in their dashboards, and you may receive a reminder notification.

---

## 7. Jira Notifications

TeamOps sends notifications through Jira's built-in notification system. You receive these in your Jira notification bell (top-right corner of Jira) and, depending on your Jira settings, by email.

### Notifications You May Receive

| Event | Who Gets Notified |
|-------|-------------------|
| **Leave request submitted** | Your manager (the approver) |
| **Leave request approved** | You (the requester) |
| **Leave request rejected** | You (the requester), with the manager's comment |
| **Leave request cancelled** | Your manager |
| **Onboarding task assigned to you** | You |
| **Onboarding task overdue** | You, your manager, and HR Admin |
| **Onboarding started** | The new hire and all task assignees |

### Managing Your Notification Preferences

TeamOps uses Jira's notification system, so your existing Jira notification preferences apply. To adjust:

1. Click your **profile avatar** in the top-right corner of Jira.
2. Select **Notification preferences**.
3. Adjust your email and in-app notification settings.

Your HR Admin may also configure which TeamOps notifications are enabled at the organization level.

---

## 8. Dashboard Gadget

TeamOps includes an **HR Snapshot** gadget that you can add to your Jira dashboard for a quick daily summary.

### What the Gadget Shows

- **Who is out today** -- Team members currently on leave
- **Pending approvals** -- (Managers only) Leave requests waiting for your decision
- **Onboarding progress** -- (Managers/HR Admins) Active onboardings and their completion status

### How to Add the Gadget to Your Dashboard

1. Go to your Jira dashboard (click **Dashboards** in the top navigation, then select your dashboard or create a new one).
2. Click the **Edit** button (pencil icon) on your dashboard.
3. Click **Add Gadget**.
4. Search for **HR Snapshot** in the gadget directory.
5. Click **Add** next to the HR Snapshot gadget.
6. The gadget appears on your dashboard. You can drag it to reposition.
7. Click **Done** to save your dashboard layout.

### Gadget Tips

- The gadget refreshes automatically so you always see current data.
- If you are a Manager, the gadget highlights any pending leave requests that need your attention.
- Click on any item in the gadget to navigate directly to that leave request or onboarding in the full TeamOps portal.

---

## Need Help?

- **For app settings or configuration issues:** Contact your HR Admin.
- **For bugs or technical problems:** Your Jira administrator can reach out to TeamOps support through the Atlassian Marketplace listing.
- **For leave policy questions:** Contact your HR department directly -- TeamOps enforces the policies your HR Admin configures, but does not set them.
