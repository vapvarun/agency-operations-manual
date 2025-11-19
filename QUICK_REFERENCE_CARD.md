# WBCOM DESIGNS - QUICK REFERENCE CARD
**Print this and keep at your desk**

---

## NEW TO THE TEAM? START HERE

**Read these 8 sections FIRST for daily clarity:**

**FOUNDATION:**
1. **Section 2A** - Who reports to whom? What's my role? Daily responsibilities?
2. **Section 2B** - When to use Slack vs Basecamp? What's client-visible?
3. **Section 4A** - How do I get tasks? Which one first? What questions to ask when unclear?
4. **Section 9A** - Can I decide this or escalate? Who do I ask?

**DAILY CHECKLISTS:**
5. **Section 4B** - Is this billable time? How to log time?
6. **Section 9B** - Is this bug urgent (P0) or can it wait (P3)?
7. **Section 21** - Is this task ready to start? (Definition of Ready)
8. **Section 21A** - What do I check in code review? What does QA test?

**These 8 sections = Everything you need for daily work.**

---

## THE 3 RULES

### Rule 1: What "Done" Means

**Developer:**
- WPCS passes (0 errors)
- Tested + screenshot attached
- Time logged

**QA:**
- No critical bugs
- Screenshots attached

**PM:**
- Client approved

### Rule 2: When Stuck

**If blocked >30 min:**
Post in Slack: "Stuck on [X], tried [Y], need help with [Z]"

**Who to ask:**
- Technical → @Lead-Dev
- Task unclear → @PM
- Client question → @PM (never client directly)

### Rule 3: Response Times

| What | When |
|------|------|
| Client question | Same day (4 hrs) |
| Help request | Same day (2 hrs) |
| Code review | 24 hours |
| QA testing | 24 hours |
| Urgent/Security | Immediately |

---

## DAILY ROUTINE

### For Developers

**Morning (10:00 AM)**
- Mark attendance: Post "✅ In - [time]" in #attendance
- Check Basecamp for new tasks
- Attend standup at 10:15 AM

**During Work**
- Update task status in Basecamp
- Ask for help if stuck >30 min

**Evening (6:30 PM)**
- Post daily update in Slack:
  ```
  ✅ Done today: [...]
  🕓 Tomorrow: [...]
  🚧 Blockers: [...]
  ```
- Log time in tracker
- Mark departure: Post "👋 Out - [time]" in #attendance

### For PM

**After Standup (10:30 AM)**
- Assign help for blockers
- 2-min project check:
  - Unassigned tasks? → Assign
  - Missing deadlines? → Add
  - Stuck tasks? → Follow up

**During Day**
- Respond to client questions (4 hrs)
- Help resolve blockers

**Evening (6:45 PM)**
- Review team updates
- Flag missing updates

**Friday (After 6:50 PM)**
- Post weekly summary in Basecamp
- Send client report

---

## MEETINGS

| Meeting | When | Duration | Focus |
|---------|------|----------|-------|
| **Daily Standup** | 10:15 AM | 15 min | Individual tasks & blockers |
| **Monday Planning** | Mon 11:00 AM | 30-45 min | PROJECT goals for the week |
| **Friday Review** | Fri 6:00 PM | 45-50 min | PROJECT progress review |
| **Client Meetings** | 3-6 PM | As needed | Client updates |

**Meeting Focus:**
- **Daily Standup:** Task-level (What I'm doing today)
- **Monday/Friday:** Project-level (How's the project doing?)

**MOM (Minutes of Meeting):**
- ✅ Required: Monday Planning, Friday Review (post in Basecamp within 2 hours)
- ❌ Not Required: Daily Standup (keep it quick)

### Monday Planning (Project-Focused)

**For EACH project, discuss:**
1. Project status & progress %
2. This week's goals
3. Task pipeline (pending/in-progress/completed)
4. Roadblocks & dependencies
5. Resource allocation

**PM posts MOM in Basecamp** with:
- Project status & timeline
- Week's goals
- Roadblocks with owners & ETAs
- Action items

### Friday Review (Project-Focused)

**For EACH project, discuss:**
1. Did we achieve Monday's goals?
2. Tasks completed vs planned
3. Roadblocks resolved/outstanding
4. Quality & client feedback
5. Next week preview

**PM posts MOM in Basecamp** with:
- Goals achievement status
- Task completion summary
- Timeline update
- Client feedback
- Next week's plan

**NOT about individual performance - focus on PROJECT health!**

---

## ATTENDANCE & LEAVE

**Daily Attendance:**
- In: Post by 10:15 AM in #attendance
- Out: Post after 7:00 PM in #attendance
- Late >3 times/month = warning

**Leave Request (Must Request 1 Day in Advance):**
```
📅 Leave Request
Name: [Your Name]
Date(s): [DD/MM/YYYY]
Type: [Casual/Sick/Annual]
Reason: [Brief]
Backup: [Name]
```

**Leave Approval Flow:**
1. Employee posts in #attendance + tags @PM
2. PM approves/rejects (within 4 hrs)
3. PM notifies HR
4. HR confirms final approval (within 24 hrs)
5. **Leave NOT final until HR confirms**

**Leave Types:**
- Casual: 12 days/year
- Sick: 10 days/year (medical cert if 3+ days)
- Annual: 15 days/year
- Emergency: Same-day (call PM, don't just message)

**Before Leave:**
- Update Basecamp tasks
- Handover notes to backup
- Set Slack status: "🏖️ On Leave [dates]"

---

## TOOLS & CHANNELS

| Tool | Purpose |
|------|---------|
| **Basecamp** | Tasks, client communication |
| **Slack** | Daily updates, team chat |
| **Time Tracker** | Log hours |
| **WPCS** | Code quality (run before commit) |
| **Plugin Checker** | Plugin standards |

**Slack Channels:**
- **#daily-updates** - End-of-day progress (mandatory)
- **#attendance** - Daily in/out, leave requests
- **#emergencies** - Site down, critical bugs

---

## WHO TO CONTACT

| Issue | Contact | See Section |
|-------|---------|-------------|
| Stuck on code | @Lead-Dev or Senior Dev | 2A, 9A |
| Task unclear | @PM or BA | 2A, 4A |
| Client question | @PM (NEVER answer directly) | 2A, 2B |
| **Client contacts me directly** | **Redirect to PM (template in 2B)** | **2B** |
| **PM unavailable** | **@Lead-Dev (PM backup)** | **2A** |
| Urgent/Security | @PM + @Lead-Dev in #emergencies | 2B, 18 |
| Leave request | Post in #attendance + @PM | 3 |
| Check leave balance | @HR | 3 |
| Which task first? | @PM | 4A |
| Can I make this decision? | See Decision Matrix | 9A |
| **Disagree with Lead Dev** | **Discuss respectfully (process in 9A)** | **9A** |
| **QA vs Dev bug dispute** | **@Lead-Dev decides** | **21A** |

**Full reporting structure & roles:** See Section 2A
**BA assists PM** with requirements - See Section 2A

---

## ESCALATION

**Stuck on task:**
```
Stuck (30 min)
    ↓
Ask in Slack
    ↓
Still stuck (2 hrs)
    ↓
PM adjusts timeline
```

**Client complaint:**
```
Client complaint
    ↓
Tell PM immediately
    ↓
PM responds (4 hrs)
```

---

## QUICK TIPS

**For Developers:**
- Run WPCS before committing: `phpcs --standard=WordPress file.php`
- Never respond to client directly
- Commit format: `[Fix] Description` or `[Feature] Description`
- Post daily update by 6:30 PM (no exceptions)

**For QA:**
- Start testing within 24 hrs of "QA Ready"
- Clear bug reports: Steps + screenshot
- Test on staging, not production

**For PM:**
- Review daily updates at 6:45 PM
- Do project board check after standup
- Client reports every Friday
- Keep Basecamp client-friendly

---

## RED FLAGS - REPORT IMMEDIATELY

**Report to PM immediately (Slack/WhatsApp):**
- Security issue
- Site down (post in #emergencies + follow Section 18)
- Client escalation
- Stuck >2 hours on urgent task
- Missing credentials to start work

**After hours:** Message PM on Slack/WhatsApp, if no response in 15 min → Message Lead Dev

---

## KEY PROCESSES (QUICK LOOKUP)

| Question | Answer in Section |
|----------|-------------------|
| Who reports to whom? | 2A - Roles & Reporting Structure |
| **What does BA do?** | **2A - BA is PM Assistant** |
| **PM unavailable - who helps?** | **2A - PM Backup (Lead Dev)** |
| When to use Slack vs Basecamp? | 2B - Communication Protocol |
| **Client contacts me directly?** | **2B - Direct Client Contact Protocol** |
| How do I get tasks? | 4A - Task Assignment |
| Task is unclear - what to ask? | 4A - Clarification Questions |
| Which task should I do first? | 4A - Task Priority Rules |
| Is this time billable? | 4B - Time Tracking Rules |
| Meetings & MOM format? | 8 - Meeting Structure |
| Can I decide this or escalate? | 9A - Decision Authority Matrix |
| **Can I challenge Lead Dev?** | **9A - Technical Disagreement Process** |
| **Deadline seems impossible?** | **9A - Timeline Communication** |
| Who do I ask when stuck? | 9A - Escalation Paths |
| Is this bug urgent? | 9B - Bug Priority (P0/P1/P2/P3) |
| New Project? | 15 - Project Onboarding |
| Ready to Deploy? | 16 - Deployment Process |
| Client wants changes? | 17 - Scope Change Process |
| Site Down? | 18 - Emergency Response |
| Git branching? | 19 - Git Workflow |
| New team member? | 20 - Team Onboarding |
| Can I start this task? | 21 - Definition of Ready |
| What to check in code review? | 21A - Code Review Checklist |
| **Who approves code review?** | **21A - Senior Dev or Lead Dev** |
| What should QA test? | 21A - QA Testing Checklist |
| **QA vs Dev disagree on bug?** | **21A - Disagreement Resolution** |
| **Test entire app or just feature?** | **21A - Regression Testing Scope** |
| **Where are test accounts?** | **21B - Test Environment Setup** |

---

## SUCCESS METRICS

**Target:**
- QA Pass Rate: 85%+
- Deadlines Met: 95%+
- Client Response: <4 hours
- Code Reviews: <24 hours

---

**Questions? Ask PM or check full manual in Basecamp.**

© 2025 WBCOM DESIGNS
