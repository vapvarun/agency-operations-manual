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

## 14. Project Onboarding Process (Starting New Projects)

When a new project/client comes in, follow this checklist to start smoothly:

### Initial Kickoff Meeting (PM + Lead Dev + Client)

**Before the meeting, PM prepares:**
- [ ] Client questionnaire sent (goals, timeline, budget)
- [ ] Review any existing documentation/materials

**During kickoff meeting (cover these):**
- [ ] Project goals and success criteria
- [ ] Timeline and key milestones
- [ ] Budget and hour allocation
- [ ] Scope boundaries (what's included, what's not)
- [ ] Who are key contacts (client side + our side)
- [ ] Communication preferences (email, Basecamp, meetings frequency)
- [ ] Access needed (hosting, domain, existing code, analytics)

**After kickoff meeting (within 24 hours):**

**PM does:**
- [ ] Create project in Basecamp
- [ ] Set up folder structure (Docs & Files → Credentials, Designs, Notes)
- [ ] Add client to Basecamp
- [ ] Post meeting summary in Basecamp
- [ ] Create initial task list with deadlines
- [ ] Assign Primary and Backup developers
- [ ] Request all credentials and access
- [ ] Set up weekly meeting schedule
- [ ] Add project to time tracker

**Lead Dev does:**
- [ ] Set up git repository
- [ ] Create development/staging environments
- [ ] Document environment setup in Basecamp
- [ ] Review technical requirements

**First week:**
- [ ] All credentials collected and stored in Basecamp
- [ ] Team has access to necessary tools
- [ ] First sprint tasks defined and assigned
- [ ] First client meeting scheduled

**Red flags to address immediately:**
- Missing credentials after 3 days → Escalate to client
- Unclear scope → Schedule clarification meeting
- Unrealistic timeline → Discuss adjustment with client

---

## 15. Deployment/Release Process (Going to Production)

### Development to Staging

**Developer (before deployment to staging):**
- [ ] Code passes WPCS locally
- [ ] All tests passing locally
- [ ] Merge feature branch to develop branch
- [ ] Push to staging server

**No approval needed for staging** - developers can deploy freely for testing.

---

### Staging to Production (Requires Approval)

**Before production deployment:**

**Developer prepares:**
- [ ] Code tested on staging thoroughly
- [ ] QA approved on staging
- [ ] Screenshot/video proof attached to Basecamp
- [ ] Database changes documented (if any)
- [ ] Backup plan documented

**Developer requests deployment:**
- [ ] Comment in Basecamp: "@PM @Lead-Dev Ready for production deployment"
- [ ] List what's being deployed
- [ ] Note any special instructions

**PM + Lead Dev review:**
- [ ] Client approved the feature
- [ ] No reported bugs on staging
- [ ] Timing is good (not Friday evening, not during client's peak hours)

**Approval given:** PM comments "Approved for production deployment"

---

### Production Deployment Checklist

**Developer executes:**
1. [ ] **Backup first** - Database and files backup
2. [ ] **Deployment window** - Inform client if downtime expected
3. [ ] **Deploy code** - Push to production
4. [ ] **Smoke test** - Check critical functionality (homepage, checkout, login, etc.)
5. [ ] **Monitor** - Watch for errors for 30 minutes
6. [ ] **Confirm in Basecamp** - "Deployed to production successfully at [time]"

**If deployment fails:**
1. [ ] **Rollback immediately** - Restore from backup
2. [ ] **Inform PM** - In Slack immediately
3. [ ] **Inform client** - PM handles communication
4. [ ] **Debug on staging** - Fix issue before retry
5. [ ] **Post-mortem** - What went wrong, how to prevent

---

### Production Deployment Rules

**✅ Can deploy immediately:**
- Small bug fixes (no database changes)
- CSS/UI tweaks
- Content updates

**⚠️ Need PM approval:**
- New features
- Database schema changes
- Third-party integrations
- Major code changes

**🚫 Never deploy without approval:**
- Friday after 3 PM (in case issues arise over weekend)
- During client's peak business hours
- Without testing on staging first
- Without backup plan

---

## 16. Scope Change/Change Request Process

Client says: "Can you add this feature?" - Follow this process:

### Step 1: Don't Commit Immediately

**Developer/PM response:**
> "That's a great idea! Let me evaluate the impact on timeline and budget and get back to you by [tomorrow/specific time]."

**Never say:** "Sure, we'll add it!" (commits you without knowing impact)

---

### Step 2: PM Evaluates Impact (Within 24 hours)

**PM asks Lead Dev/Developer:**
- How many hours will this take?
- Does it affect current timeline?
- Any technical dependencies or risks?

**PM calculates:**
- [ ] Hours required
- [ ] Impact on current deadline
- [ ] Budget availability (hours remaining on project)
- [ ] Priority vs current tasks

---

### Step 3: PM Responds to Client

**Option A: Small change, budget available**
> "We can add this! It will take approximately [X hours]. This fits within your current budget. We'll have it ready by [date]. Sound good?"

**Option B: Larger change, no budget**
> "Great idea! This would take approximately [X hours]. This would require [additional hours/budget]. Would you like us to:
> 1. Add it now with additional budget?
> 2. Add it to next sprint/phase?
> 3. Replace it with a lower-priority task?"

**Option C: Change affects timeline**
> "We can do this, but it will push the deadline from [original date] to [new date]. Are you okay with that adjustment?"

---

### Step 4: Get Written Approval

**Before starting work:**
- [ ] Client approves in Basecamp or email (written record)
- [ ] If budget change → get approval from management
- [ ] Update project timeline in Basecamp
- [ ] Update task list with new scope

---

### Step 5: Execute and Track

- [ ] Create new task in Basecamp
- [ ] Assign developer
- [ ] Log time separately (track scope change hours)
- [ ] Keep client updated on progress

---

### When to Say "No" or "Later"

**Say "Later" when:**
- Hours budget exhausted
- Will miss critical deadline
- Conflicts with current priorities

**Say "No" when:**
- Technically not feasible
- Security risk
- Outside project scope entirely
- Client wants to bypass quality process

**How to say no politely:**
> "I understand this is important. However, [reason]. I recommend we add this to the next phase/sprint. Would that work?"

---

### Preventing Scope Creep

**PM monitors:**
- Track "scope change" hours separately
- If >20% of project is scope changes → discuss with client
- Weekly review: "Are we adding too much?"
- Document everything in Basecamp (verbal requests = write them down)

---

## 17. Emergency/Crisis Response

### What Counts as Emergency

**Immediate Response (within 30 min):**
- Production site completely down
- Security breach or hack
- Data loss
- Payment system not working
- Critical bug affecting all users

**Urgent (within 2 hours):**
- Major feature broken
- Performance extremely slow
- Bug affecting many users

**Not Emergency:**
- Small visual bugs
- Feature requests
- Minor delays

---

### Emergency Response Process

**Step 1: Alert the Team (Immediately)**

**Whoever discovers issue:**
1. Post in Slack `#emergencies` channel: "🚨 EMERGENCY: [brief description]"
2. Tag: @PM @Lead-Dev @on-duty-developer
3. If after hours: Call PM directly (phone number in Basecamp)

**Example:**
> "🚨 EMERGENCY: Client XYZ's site is completely down. Getting 500 error. Discovered at 3:45 PM."

---

**Step 2: PM Takes Command (Within 15 min)**

**PM assigns:**
- [ ] Lead Dev + 1 Developer: Fix the issue
- [ ] PM: Handle client communication
- [ ] Other team members: Continue regular work (unless critical)

**PM updates client immediately:**
> "We're aware of the issue with [description]. Our team is investigating now. I'll update you within 30 minutes."

---

**Step 3: Diagnose and Fix (ASAP)**

**Dev team:**
- [ ] Check error logs
- [ ] Identify root cause
- [ ] Test fix on staging (if time permits)
- [ ] Apply fix to production
- [ ] Monitor for 30 minutes

**PM updates client every 30 minutes:**
> "Update: We've identified the issue was [cause]. Currently implementing fix. ETA: 30 minutes."

---

**Step 4: Verify Resolution**

- [ ] Site/feature working normally
- [ ] Smoke test critical functionality
- [ ] Monitor logs for errors
- [ ] PM confirms with client: "Issue resolved. Please verify on your end."

---

**Step 5: Post-Incident Review (Within 24 hours)**

**PM + Lead Dev + Developer(s) involved:**

**Document in Basecamp:**
1. **What happened?** (timeline of events)
2. **Root cause?** (why it happened)
3. **How fixed?** (solution applied)
4. **How to prevent?** (process/code changes needed)
5. **Action items** (assign owners and deadlines)

**Example:**
> **Incident:** Site down due to plugin conflict
> **Cause:** Auto-update enabled, plugin updated without testing
> **Fix:** Rolled back plugin, disabled auto-updates
> **Prevention:** Disable auto-updates on all production sites (Action: Lead Dev, by Friday)

---

### Emergency Contact Info

**Keep this updated in Basecamp:**

| Role | Name | Slack Handle | WhatsApp | Availability |
|------|------|--------------|----------|--------------|
| PM | [Name] | @pm-name | Available | 9 AM - 10 PM |
| Lead Dev | [Name] | @leaddev-name | Available | 9 AM - 10 PM |
| Backup Dev | [Name] | @backupdev-name | Available | 9 AM - 8 PM |
| Management | [Name] | @mgmt-name | Available | Emergency only |

**After-hours emergencies:**
- Message PM in Slack/WhatsApp first (mark as urgent)
- If no response in 15 min → Message Lead Dev
- If no response in 30 min → Message Management
- Tag @channel in #emergencies Slack channel

---

### Emergency Communication Templates

**To Client (Site Down):**
> "We've identified an issue with [site/feature]. Our team is actively working on it. We expect resolution within [timeframe]. I'll update you every 30 minutes. Apologies for the disruption."

**To Client (Issue Resolved):**
> "The issue has been resolved. [Brief explanation of cause]. We've implemented [fix] and monitored for stability. We're also taking steps to prevent this: [prevention measures]. Again, apologies for the disruption."

---

## 18. Git Workflow & Branching Strategy

### Branch Structure

**Main Branches (Always exist):**
- `main` - Production code (always stable)
- `develop` - Development integration branch (for staging)

**Temporary Branches (Created as needed):**
- `feature/description` - New features
- `bugfix/description` - Bug fixes
- `hotfix/description` - Emergency production fixes

---

### Branch Naming Conventions

**Good examples:**
- `feature/user-profile-export`
- `feature/add-payment-gateway`
- `bugfix/checkout-duplicate-order`
- `bugfix/dashboard-loading-slow`
- `hotfix/critical-security-patch`

**Bad examples:**
- `john-work` (unclear what it is)
- `fix` (too vague)
- `testing123` (not descriptive)

---

### Workflow for New Feature/Bug Fix

**Step 1: Create Branch**

```bash
# Start from develop branch
git checkout develop
git pull origin develop

# Create your feature branch
git checkout -b feature/user-profile-export
```

---

**Step 2: Work on Your Branch**

```bash
# Make changes, commit often
git add .
git commit -m "[Feature] Add user profile export functionality"

# Push to remote regularly
git push origin feature/user-profile-export
```

**Commit Message Format:**
- `[Feature] Description` - New functionality
- `[Fix] Description` - Bug fix
- `[Update] Description` - Enhance existing feature
- `[Refactor] Description` - Code improvement (no behavior change)
- `[Docs] Description` - Documentation only

---

**Step 3: Keep Branch Updated**

If working on branch for multiple days:

```bash
# Pull latest changes from develop
git checkout develop
git pull origin develop

# Merge into your branch
git checkout feature/user-profile-export
git merge develop

# Resolve conflicts if any, then push
git push origin feature/user-profile-export
```

---

**Step 4: Ready for Review**

**When feature complete:**
- [ ] Code passes WPCS locally
- [ ] Tested locally
- [ ] Commit and push all changes
- [ ] Create task comment in Basecamp: "Ready for code review - branch: feature/user-profile-export"
- [ ] Tag peer reviewer

---

**Step 5: Peer Review**

**Reviewer checks out branch:**

```bash
git fetch origin
git checkout feature/user-profile-export
# Test the feature
```

**Reviewer checks:**
- [ ] Code follows standards
- [ ] No obvious bugs
- [ ] Logic makes sense
- [ ] Proper error handling

**If approved:** Comment in Basecamp "Code review approved - ready to merge"
**If issues:** Comment specific issues, developer fixes and re-requests review

---

**Step 6: Merge to Develop (Staging)**

**Developer merges:**

```bash
git checkout develop
git pull origin develop
git merge feature/user-profile-export
git push origin develop
```

**Then deploy to staging for QA testing.**

---

**Step 7: Merge to Main (Production)**

**After QA approval and PM approval:**

```bash
git checkout main
git pull origin main
git merge develop
git push origin main
```

**Then deploy to production.**

---

**Step 8: Delete Feature Branch**

**After successfully in production:**

```bash
git branch -d feature/user-profile-export
git push origin --delete feature/user-profile-export
```

Keeps repo clean.

---

### Hotfix Workflow (Emergency Production Fix)

**If critical bug in production:**

```bash
# Create hotfix branch from main
git checkout main
git pull origin main
git checkout -b hotfix/critical-security-patch

# Fix the issue, test thoroughly
git add .
git commit -m "[Hotfix] Fix critical security vulnerability"

# Merge to main
git checkout main
git merge hotfix/critical-security-patch
git push origin main

# Also merge to develop (keep in sync)
git checkout develop
git merge hotfix/critical-security-patch
git push origin develop

# Delete hotfix branch
git branch -d hotfix/critical-security-patch
```

**Deploy to production immediately.**

---

### Git Rules

**✅ DO:**
- Create branch for every task
- Commit often with clear messages
- Pull from develop before merging
- Delete branches after merge
- Keep commits small and focused

**🚫 DON'T:**
- Commit directly to main or develop
- Push broken code
- Leave branches open forever
- Use vague commit messages
- Commit sensitive data (passwords, API keys)

---

### Handling Merge Conflicts

**If you get merge conflict:**

1. **Don't panic** - conflicts are normal
2. **Ask for help** - Tag Lead Dev if unclear
3. **Resolve carefully** - Don't delete others' code
4. **Test after resolving** - Make sure nothing broken
5. **Ask for review** - If conflict was complex

---

## 19. New Team Member Onboarding

When a new developer, QA, or PM joins the team, follow this checklist to onboard them smoothly:

### Before First Day (HR + PM)

**HR prepares:**
- [ ] Employment paperwork completed
- [ ] Workstation/laptop ready
- [ ] Email account created
- [ ] Add to Slack workspace
- [ ] Add to company WhatsApp group

**PM prepares:**
- [ ] Add to Basecamp (all relevant projects)
- [ ] Add to time tracker
- [ ] Assign mentor/buddy (experienced team member)
- [ ] Prepare first-week task list (simple, low-risk tasks)
- [ ] Add to team calendar

---

### First Day Checklist

**Morning (9:30 AM - 12:00 PM)**

**HR does (30 min):**
- [ ] Office tour
- [ ] Introduce to team
- [ ] Review office policies (hours, leave, attendance)
- [ ] Provide this Operations Manual
- [ ] Provide Quick Reference Card

**PM does (1 hour):**
- [ ] Welcome meeting (introduce team structure, roles)
- [ ] Explain tools (Basecamp, Slack, Time Tracker)
- [ ] Review daily/weekly meeting schedule
- [ ] Show where credentials stored (Basecamp → Docs & Files)
- [ ] Explain daily update process (Slack at 6:30 PM)
- [ ] Assign mentor/buddy

**Lead Dev does (1 hour) - For Developers:**
- [ ] Setup development environment
- [ ] Grant git repository access
- [ ] Explain git workflow (Section 18)
- [ ] Setup local WordPress/testing environment
- [ ] Install WPCS + Plugin Checker
- [ ] Review code quality standards
- [ ] Clone existing projects

**Lunch Break (12:00 PM - 1:00 PM)**
- Team lunch with new member

**Afternoon (1:00 PM - 5:00 PM)**

**Mentor/Buddy does:**
- [ ] Sit together and answer questions
- [ ] Walk through 1-2 existing projects in Basecamp
- [ ] Help with any tool setup issues
- [ ] Explain team communication norms
- [ ] Show example of good Basecamp task update
- [ ] Show example of good git commit

**New member does:**
- [ ] Read Operations Manual (Sections 1-3, 14-24)
- [ ] Complete first simple task (guided by mentor)
- [ ] Post first daily standup update at 6:30 PM

---

### First Week (Day 2-5)

**Daily:**
- [ ] Attend standup at 10:15 AM
- [ ] Work on assigned tasks (mentor available for questions)
- [ ] Post daily updates by 6:30 PM
- [ ] Log time in tracker

**By End of Week:**
- [ ] Completed 2-3 simple tasks
- [ ] Understands git workflow
- [ ] Understands Basecamp task flow
- [ ] Knows who to ask for what (PM, Lead Dev, mentor)
- [ ] Attended first Friday weekly review

**PM checks in (30 min end-of-week):**
- "How's your first week going?"
- "Any questions or confusion?"
- "Do you have everything you need?"
- "Anything we can improve in onboarding?"

---

### First Month

**Week 2-4:**
- [ ] Gradually increase task complexity
- [ ] Assign as backup developer on 1 project
- [ ] Continue mentor support (but less hand-holding)
- [ ] Participate actively in meetings

**By End of Month:**
- [ ] Working independently on medium tasks
- [ ] Comfortable with all tools and processes
- [ ] Knows when/how to ask for help
- [ ] Zero missed daily updates
- [ ] Completed peer code review for colleague

**PM does end-of-month review (30 min):**
- Review first month performance
- Discuss strengths and areas to improve
- Get feedback on onboarding process
- Set goals for next month

---

### Onboarding Checklist by Role

#### For Developers:
- [ ] Development environment setup
- [ ] Git access and workflow training
- [ ] WPCS + Plugin Checker installed
- [ ] Code review process explained
- [ ] Completed first git branch → merge cycle
- [ ] Understands Definition of Done (Section 20)

#### For QA:
- [ ] Staging server access
- [ ] Testing checklist provided
- [ ] Bug reporting format explained
- [ ] Understands QA criteria (Section 20)
- [ ] Cross-browser testing tools setup
- [ ] Completed first full testing cycle

#### For PM:
- [ ] All client project access
- [ ] Client communication guidelines reviewed
- [ ] Weekly report template provided
- [ ] Shadowed senior PM for 1 week
- [ ] Led first client meeting (with supervision)
- [ ] Understands all processes (Sections 14-18)

---

### Red Flags in Onboarding

**If you see these, address immediately:**

| Red Flag | Action |
|----------|--------|
| New member missing daily updates | Mentor reminds gently, explain importance |
| Confused about process after 1 week | Extra training session with PM |
| Not asking questions at all | Mentor proactively checks in ("Any questions?") |
| Tasks taking 2x longer than expected | Pair programming with mentor, check skill level |
| Uncomfortable with tools after 2 weeks | One-on-one training session |
| Not integrating with team | Team lunch, informal bonding |

---

### First Month Checklist (Manager)

**End of Month 1:**
- [ ] New member completed onboarding checklist
- [ ] Can work independently on simple tasks
- [ ] Understands all core processes
- [ ] Comfortable with tools
- [ ] Integrating well with team
- [ ] Receiving positive mentor feedback

**If checklist not complete:** Extend probation, provide additional training, or evaluate fit.

---

## 20. Definition of Done (What "Complete" Actually Means)

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

## 21. When You're Stuck (Simple Escalation)

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

## 22. Response Time Expectations

| What | Response Time | Who Responds |
|------|---------------|--------------|
| Client question (Basecamp) | Same day (within 4 hours) | PM |
| Developer help request | Same day (within 2 hours) | PM or Lead Dev |
| Peer code review | Within 24 hours | Peer Developer |
| QA testing start | Within 24 hours of "QA Ready" | QA Team |
| Security/Critical bug | Immediately (within 30 min) | Everyone |

*If you can't meet the deadline, reply: "Got it, will respond by [time]"*

---

## 23. Daily Standup Structure (10:15 AM – 10:35 AM)

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

## 24. Weekly Review Structure (Friday 6:00 PM – 6:50 PM)

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

## 25. Document Control

- **Owner:** HR & Project Management Team
- **Version:** 4.0
- **Last Updated:** November 2025
- **Next Review:** February 2026
- **Changelog:**
  - v4.0: Added Team Member Onboarding, Updated Emergency Contacts (Slack/WhatsApp)
  - v3.0: Added 5 critical processes (Project Onboarding, Deployment, Scope Change, Emergency Response, Git Workflow)
  - v2.0: Added Definition of Done, Escalation, Response Times, Meeting Structures
  - v1.0: Initial manual (October 2025)

---

© 2025 WBCOM DESIGNS. All Rights Reserved.
