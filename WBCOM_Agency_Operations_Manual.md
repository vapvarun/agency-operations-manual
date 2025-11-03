# WBCOM DESIGNS - AGENCY PROJECT OPERATIONS MANUAL

This document defines the complete management, communication, and evaluation system for Wbcom Designs. It ensures consistent operations, quality assurance, accountability, and transparent client communication for all projects.

---

## 1. Foundation of the System

Every task, meeting, and deliverable runs on time with visible ownership and backup coverage — managed purely through Basecamp and Slack. All activities must be logged in these two tools to ensure traceability and accountability.

> “If it’s not updated in Basecamp or Slack, it didn’t happen.”

---

## 2. Office & Working Hours

- **Office Timing:** 10:00 AM – 7:00 PM
- **Daily Standup:** 10:15 AM – 10:30 AM
- **Client Meetings:** 3:00 PM – 6:00 PM (scheduled by PM)
- **Weekly Review:** Friday, 6:00 PM – 6:50 PM

Leave must be informed at least one day in advance via Slack in the `#attendance` or `#team-updates` channel.

**Core Tools:** Basecamp (projects), Slack (updates), Time Tracker (hours), WPCS + Plugin Checker (code quality)

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

## 14. Definition of Done (What "Complete" Actually Means)

A task is only "Complete" when ALL criteria are met:

### Developer (Before marking "Peer Review"):
- [ ] Code passes WPCS check (run locally: `phpcs --standard=WordPress`)
- [ ] Plugin Checker shows no errors
- [ ] Tested on local/staging + screenshot attached to Basecamp
- [ ] Time logged in time tracker
- [ ] Git commit with clear message (format: `[Type] Description`)

### QA (Before marking "Done"):
- [ ] All critical bugs fixed (no P0/P1 bugs remaining)
- [ ] Test screenshots attached to Basecamp
- [ ] Cross-browser tested (if UI change)

### PM (Before marking "Complete"):
- [ ] Client approved or demo completed
- [ ] Task closed in Basecamp

---

## 15. When You're Stuck (Simple Escalation)

**If blocked on a task:**

1. **Try yourself (30 minutes max)** - Search docs, check similar past tasks
2. **Ask for help immediately** - Post in Slack: "Stuck on [task], tried [what], need help with [specific question]"

**Who to contact:**
- **Technical question** → Lead Developer
- **Task unclear** → PM
- **Client question** → PM only (never ask client directly)
- **Urgent/critical issue** → PM + Lead Dev immediately

**Rule:** Don't waste time being stuck. If blocked >30 minutes, ask for help.

---

## 16. Response Time Expectations

| What | Response Time | Who Responds |
|------|---------------|--------------|
| Client question (Basecamp) | Same day (within 4 hours) | PM |
| Developer help request | Same day (within 2 hours) | PM or Lead Dev |
| Peer code review | Within 24 hours | Peer Developer |
| QA testing start | Within 24 hours of "QA Ready" | QA Team |
| Security/Critical bug | Immediately (within 30 min) | Everyone |

*If you can't meet the deadline, reply: "Got it, will respond by [time]"*

---

## 17. Daily Standup Structure (10:15 AM – 10:35 AM)

**Duration:** 15 minutes MAX

### Format (Round-Robin)
Each person answers (1 minute per person):
1. ✅ **What did you complete yesterday?**
2. 🕓 **What are you working on today?**
3. 🚧 **Any blockers?**

### After Standup (5 minutes)
**PM addresses blockers:**
- Technical blocker → Lead Dev helps
- Waiting on client → PM follows up
- Task unclear → PM clarifies

**PM does 2-minute project board check:**
- Any unassigned tasks? → Assign immediately
- Any tasks without deadlines? → Add deadline now
- Any tasks stuck in "To Do" for 3+ days? → Follow up

---

## 18. Weekly Review Structure (Friday 6:00 PM – 6:50 PM)

**Duration:** 50 minutes MAX

### Agenda (Time-Boxed):

**Part 1: Quick Wins (10 min)**
- PM shares what went well this week
- Recognize team achievements

**Part 2: Check The 3 Rules (15 min)**

*Rule 1: Definition of Done*
- "Did everyone run WPCS before peer review?"
- "QA pass rate this week?" (Target: 85%+)

*Rule 2: Getting Help When Stuck*
- "Did anyone stay stuck >30 min without asking?"
- "Did everyone who asked get help same day?"

*Rule 3: Response Times*
- "Any client questions unanswered >4 hours?"
- "Any code reviews pending >24 hours?"

**Part 3: This Week's Problems (10 min)**
- What slowed us down?
- How do we prevent it next week?

**Part 4: Project/Product Review (5 min)**

*For each active project, PM checks:*
1. **Unassigned tasks?** → Assign now or move to backlog
2. **Tasks stuck 5+ days?** → Why? Reassign or clarify
3. **Project-level blockers?** → PM resolves by specific date
4. **Team confused about direction?** → Schedule client clarification
5. **Anyone overloaded?** → Redistribute workload

**Part 5: Next Week Planning (5 min)**
- Upcoming deadlines
- Client meetings scheduled
- Anyone on leave?

**Part 6: Open Floor (5 min)**
- Team suggestions or questions

### After Weekly Review:
PM posts summary in Basecamp + creates client report with completed tasks and hours used.

---

## 19. Document Control

- **Owner:** HR & Project Management Team
- **Version:** 2.0
- **Last Updated:** November 2025
- **Next Review:** February 2026
- **Changelog:**
  - v2.0: Added Definition of Done, Escalation, Response Times, Meeting Structures
  - v1.0: Initial manual (October 2025)

---

© 2025 WBCOM DESIGNS. All Rights Reserved.
