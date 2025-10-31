# WBCOM DESIGNS - AGENCY PROJECT OPERATIONS MANUAL (FINAL EDITION)

This document defines the complete management, communication, and evaluation system for Wbcom Designs. It ensures consistent operations, quality assurance, accountability, and transparent client communication for all projects.

---

## 1. Foundation of the System

Every task, meeting, and deliverable runs on time with visible ownership and backup coverage — managed purely through Basecamp and Slack. All activities must be logged in these two tools to ensure traceability and accountability.

> “If it’s not updated in Basecamp or Slack, it didn’t happen.”

---

## 2. Office & Working Hours

- **Office Timing:** 10:00 AM – 7:00 PM  
- **Daily Standup:** 10:15 AM  
- **Client Meetings:** 3:00 PM – 6:00 PM (scheduled by PM)  
- **Weekly Review:** Friday, 6:00 PM – 6:45 PM  

Leave must be informed at least one day in advance via Slack in the `#attendance` or `#team-updates` channel.

---

## 3. Task & Deadline System (Manual Tracking)

- All tasks are assigned in Basecamp with clear **titles, deadlines, descriptions, and assigned developers**.  
- Each task must include:
  - Start Date & End Date  
  - Priority (High/Medium/Low)  
  - Backup Developer  

**Daily Accountability:** Developers must post end-of-day updates in Slack’s `#daily-updates` channel.

```
✅ What was completed today
🕓 What will be done tomorrow
🚧 Any blockers or dependencies
```

---

## 4. Strict Deadline Enforcement

| Stage | Action | Responsible |
|--------|---------|-------------|
| Task assigned | PM confirms realistic timeline | PM |
| Daily progress | Developer posts update in Slack | Developer |
| Missed deadline (Day 1) | PM flags issue in Slack | PM |
| Missed twice | PM & Lead review reason | PM & Lead |
| Repeated delay | Written warning and review | Management |

- **No extensions** without PM approval.  
- Two missed deadlines in a sprint → review with PM.

---

## 5. Handling Absences & Backup Coverage

- Every project has a **Primary Developer** and **Backup Developer** in Basecamp.  
- If the primary is absent, the backup takes over after PM confirmation.  
- PM ensures Basecamp handover notes are always current.

---

## 6. Managing Client Workload Variations

### When Client Provides Fewer Tasks
Developers use idle time for:
- Documentation updates
- Optimization or learning
- Helping QA or peers

### When Client Provides Too Many Tasks but Low Billing
- PM reviews and prioritizes tasks by billing hours.  
- Only approved or essential items are completed that week.  
- PM communicates limits clearly and politely to the client.

---

## 7. Meeting Structure

| Meeting | Frequency | Attendees | Purpose | Notes |
|----------|------------|------------|----------|--------|
| Daily Standup | Daily (10:15 AM) | All Devs + PM | Discuss blockers and tasks | Post summary if absent |
| Weekly Review | Friday (6:00 PM) | PM + Leads + QA | Review performance | Summary in Basecamp |
| Client Meeting | Weekly | PM + Assigned Dev | Client progress & feedback | Document in Basecamp |

---

## 8. Quality & Review Enforcement

Every task passes through: **Developer → Peer Review → QA → PM Approval → Client Review**.

**Code & QA Rules:**
- Follow WPCS and modular coding.  
- Test locally/staging before marking done.  
- Maintain proper commit messages and documentation.  

---

## 9. Reporting & Visibility

**Daily:** Developers post updates in Slack.  
**Weekly:** PM summarizes progress in Basecamp.  
**Monthly:** PM and Leads conduct performance review meetings.

---

## 10. Manual Self-Driven Workflow Summary

1. PM assigns and reviews tasks in Basecamp.  
2. Developers acknowledge and update in Slack.  
3. Backup developers handle absences.  
4. Meetings reinforce accountability.  
5. PM maintains weekly and monthly reports.  

---

## 11. Frequently Asked Questions (FAQs)

### General
- **Tools Used:** Basecamp for projects, Slack for communication, Git for code.  
- **Missed Updates:** Daily status must be posted by 6:45 PM.  
- **Leave Policy:** Inform PM and team in Slack at least 1 day prior.

### Developers
- Post daily updates in Slack `#daily-updates`.  
- Never discuss blockers or delays with clients directly.  
- All Basecamp comments must be **client-friendly**.  
- If client gives extra tasks → inform PM only.

### QA
- Begin testing once a task is marked *Ready for QA*.  
- Report bugs with clear description and screenshots.  
- Keep communication professional in Basecamp.

### Project Managers
- Collect daily updates from developers.  
- Always maintain client-friendly tone.  
- Post weekly progress and monthly summaries.

---

## 12. Repository, Access & Client Communication Policy

### A. Repository & Access Management

- Each project has a **dedicated Git repository** (`main`, `develop`, `feature/*`, `bugfix/*`).  
- All credentials (WP Admin, SFTP, Hosting, Analytics) stored in **Basecamp → Docs & Files → "Project Credentials"**.  
- Credentials file format: `Credentials_<ProjectName>_<Date>.txt`.  
- Staging and live site credentials kept separately.  
- Weekly backups scheduled and logged in Basecamp.

### B. Client Communication Protocol

- **1 Weekly Meeting** between PM + Developer + Client (3–6 PM).  
- **Meeting Summary Format:**

```
Client Meeting Summary – <Date>
✅ Completed: [...]
🕓 In Progress: [...]
🔜 Next Week Plan: [...]
💬 Notes: [...]
```

- PM posts summary in Basecamp (client-visible).  
- Internal matters → Slack only.

### C. Basecamp Documentation Structure

| Section | Purpose |
|----------|----------|
| To-Do List | Task tracking |
| Docs & Files | Credentials, designs, SOW, notes |
| Message Board | Client communication |
| Campfire / Slack | Internal discussion |
| Schedule | Meetings & milestones |

### D. Communication Etiquette

- Keep comments short, polite, and factual.  
- Avoid internal frustrations in client threads.  
- End messages positively.

### E. Example Weekly Flow

| Day | Action | Channel |
|------|--------|----------|
| Monday | Review client feedback | Slack |
| Tue–Thu | Task execution | Basecamp + Slack |
| Friday | Client meeting | Basecamp |
| Saturday | Optional documentation | Internal only |

---

## 13. Performance Evaluation & HR Guidelines

### A. Purpose
Ensures fair, measurable, and transparent performance evaluation for all employees.

### B. Evaluation Frequency
- **Monthly:** PM + HR review.  
- **Quarterly:** Formal feedback session.  
- **Annually:** Promotion or salary review.

### C. Evaluation Categories

| Category | Description | Source |
|-----------|--------------|---------|
| Task Delivery | Timeliness of work | Basecamp logs |
| Quality | QA pass rate | QA reports |
| Communication | Slack & Basecamp tone | PM feedback |
| Initiative | Problem-solving & improvement | Peer review |
| Attendance | Consistency | HR records |

### D. Role-Based KPIs

#### Project Manager
| KPI | Target |
|------|--------|
| Client Satisfaction | ≥ 90% positive |
| On-Time Reporting | 100% |
| Deadline Management | ≥ 95% |
| Coordination | ≤ 2 escalations per month |

#### Developer
| KPI | Target |
|------|--------|
| Task Completion | ≥ 90% |
| QA Pass Rate | ≥ 85% |
| Code Quality | Verified by Lead |
| Communication | 100% daily updates |

#### QA
| KPI | Target |
|------|--------|
| Testing Coverage | 100% |
| Defect Accuracy | ≥ 95% |
| QA Timeliness | ≤ 24 hrs per task |

### E. HR Evaluation Template

| Employee Name | Role | Month | Timeliness (5) | Quality (5) | Communication (5) | Initiative (5) | Attendance (5) | Overall Score | Remarks |
|----------------|------|--------|----------------|--------------|-------------------|----------------|----------------|----------------|----------|
| | | | | | | | | | |

> 5 = Excellent | 4 = Strong | 3 = Satisfactory | 2 = Needs Improvement | 1 = Unsatisfactory

### F. HR Review Workflow

1. HR collects PM reports at month-end.  
2. Scores filled in the evaluation sheet.  
3. Underperformers (<3 average) placed on **30-day PIP**.  
4. Recognition for top performers given in monthly meeting.

### G. Behavioral Standards
- Respect all team and client communications.  
- Be punctual and professional.  
- Avoid internal issues in public spaces.  
- Contribute ideas during retrospectives.

### H. Recognition & Rewards

| Award | Criteria |
|--------|-----------|
| Performer of the Month | Consistent delivery |
| Zero Bug Champion | Clean QA results |
| Best Communicator | Professional tone |

---

## 14. Document Control

- **Owner:** HR & Project Management Team  
- **Last Updated:** October 2025  
- **Next Review:** January 2026  

---

© 2025 WBCOM DESIGNS. All Rights Reserved.
