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

**Core Tools:** Basecamp (projects), Slack (updates), Time Tracker (hours), WPCS + Plugin Checker (code quality)

---

## 2A. Roles, Responsibilities & Reporting Structure

**Purpose:** Define exactly who does what, who reports to whom, and what authority each role has. This ensures everyone knows their responsibilities and accountability without constant supervision.

---

### Team Structure & Reporting Lines

```
Management/Founders
       ↓
   Project Manager (PM)
       ↓
   ├── Business Analyst (BA) [PM Assistant]
   │
   ├── Lead Developer
   │   ↓
   │   ├── Senior Developer(s)
   │   │   ↓
   │   │   └── Junior Developer(s)
   │
   ├── QA Lead
   │   ↓
   │   └── QA Engineer(s)
   │
   └── Designer (if applicable)
```

**Reporting Frequency:**
- BA → PM: Daily (via standup + Slack updates)
- Developers → Lead Dev: Daily (via standup + Slack updates)
- Lead Dev → PM: Daily (via standup + Slack)
- QA → QA Lead or PM: Daily (via standup + Slack)
- PM → Management: Weekly (Friday summary)

---

### Role Definitions & Daily Responsibilities

#### **Management/Founders**

**Primary Responsibility:** Business strategy, client relationships at executive level, team growth

**Daily Activities:**
- Review project health (high-level)
- Handle escalations from PM
- Approve major decisions (hiring, firing, large contracts)
- Client relationship management (C-level)

**Reports To:** N/A (top of hierarchy)
**Reports From:** PM, HR

**Decision Authority:**
- ✅ Can approve: Hiring, budget allocation, salary changes, major contract terms, company policies
- ❌ Should not: Assign individual tasks, interfere in daily operations, override PM on task-level decisions

---

#### **Project Manager (PM)**

**Primary Responsibility:** Project delivery, client communication, team coordination, timeline management

**Daily Activities:**
- 10:15 AM: Lead daily standup
- Check Basecamp for client messages (respond within 4 hours)
- Assign/prioritize tasks for the day
- Unblock developers (get client approvals, clarify requirements)
- Monitor project timelines and deadlines
- 6:45 PM: Review team's daily updates in Slack #dailymeeting
- Update project status in Basecamp

**Weekly Activities:**
- Monday 11:00 AM: Weekly planning meeting (Section 8)
- Client meetings (schedule and lead)
- Friday 6:00 PM: Weekly review meeting (Section 8)
- Friday 7:00 PM: Post weekly summary in Basecamp
- Send client weekly report

**Monthly Activities:**
- Project performance review with Management
- Team performance input to HR
- Client satisfaction check-ins

**Reports To:** Management
**Reports From:** Lead Dev, QA Lead, Developers (via standup)

**Decision Authority:**
- ✅ Can approve: Task prioritization, scope changes (minor), timeline adjustments (within reason), leave requests, client communication, deployment timing
- ❌ Must escalate to Management: Budget changes, timeline delays >1 week, scope changes (major), contract modifications, team conflicts (unresolved)

**Key Metrics:**
- Client satisfaction
- On-time delivery rate
- Team utilization
- Budget adherence

**PM Backup & Unavailability:**

When PM is unavailable (sick/leave/meeting/off-hours), the following backup protocols apply:

**For Technical Questions:**
→ Contact: Lead Developer

**For Task Clarification:**
→ Technical aspects: Ask Lead Developer
→ Client-facing questions: Tag PM in Basecamp (PM will respond when available)
→ If urgent and PM unreachable: Lead Dev responds: "We've received your question and PM will respond by [time]"

**For Urgent Client Questions/Issues:**
→ Lead Developer can respond in Basecamp with:
   - Technical updates
   - Status updates on work in progress
   - Acknowledgment with timeline for PM response
→ Lead Dev informs PM when available
→ For non-technical client questions: "PM will respond by [time]"

**For Leave Approvals (when PM on leave):**
→ Backup approver: [Designate: Lead Dev or another PM or Management]
→ Same approval process applies
→ Backup informs PM upon return

**For Emergency Issues (Site Down, Critical Bug):**
→ Lead Developer handles technical response (Section 18)
→ Lead Developer updates client in Basecamp if needed
→ Inform PM immediately (WhatsApp/Phone even if on leave)

**PM Responsibilities Before Leave:**
1. Announce in Slack #general: "On leave [dates], contact @Lead-Dev for urgent issues"
2. Update Slack status: "🏖️ On Leave [dates] - Contact @Lead-Dev"
3. Brief Lead Dev on active client issues/concerns
4. Delegate time-sensitive approvals to backup
5. Set email auto-reply pointing to Lead Dev

**What Lead Dev CAN Do as PM Backup:**
✅ Technical clarifications to clients
✅ Status updates on work in progress
✅ Emergency response coordination
✅ Daily standup (if PM absent)
✅ Acknowledge urgent client messages
✅ Approve leave requests (if designated)

**What Lead Dev CANNOT Do Without PM:**
❌ Commit to new scope or deadlines
❌ Negotiate pricing or contracts
❌ Make major project decisions
❌ Approve production deployments (unless emergency)

---

#### **Lead Developer**

**Primary Responsibility:** Technical leadership, code quality, architecture decisions, developer mentoring

**Daily Activities:**
- Attend 10:15 AM standup
- Review code (peer reviews)
- Unblock developers (technical issues)
- Ensure coding standards followed (WPCS, quality checks)
- Escalate blockers to PM (if client-side or scope-related)
- Post daily update by 6:30 PM in Slack

**Weekly Activities:**
- Monday 11:00 AM: Attend weekly planning meeting
- Technical planning for complex features
- Review git branches and merge requests
- Friday 6:00 PM: Attend weekly review

**Monthly Activities:**
- Code review retrospective (what patterns are causing bugs?)
- Technology updates (evaluate new tools/frameworks)
- Developer skill assessment (provide input to PM/HR)

**Reports To:** PM
**Reports From:** Senior/Junior Developers

**Decision Authority:**
- ✅ Can approve: Technical approach, framework/library choices, code architecture, peer review approvals, developer task assignment (technical aspects)
- ✅ Can do without approval: Deploy to staging (no approval needed)
- ❌ Must escalate to PM: Timeline changes, scope clarifications, client questions, deployment to production (needs PM approval per Section 16)

**Key Metrics:**
- Code quality (QA pass rate, bug count)
- Peer review turnaround time (<24 hours)
- Developer productivity
- Technical debt management

---

#### **Senior Developer**

**Primary Responsibility:** Independent feature development, code reviews, mentoring junior developers

**Daily Activities:**
- Attend 10:15 AM standup
- Work on assigned tasks (complex features)
- Conduct peer code reviews (when assigned)
- Mentor junior developers (answer questions, pair programming)
- Update Basecamp task status throughout the day
- Post daily update by 6:30 PM in Slack
- Log time in time tracker

**Weekly Activities:**
- Participate in Monday weekly planning
- Participate in Friday weekly review

**Reports To:** Lead Developer
**Reports From:** May mentor junior developers (informal)

**Decision Authority:**
- ✅ Can decide: Technical implementation details, which libraries to use (within approved stack), code refactoring
- ✅ Can do without approval: Deploy to staging (after local testing - no approval needed)
- ❌ Must escalate to Lead Dev: Architecture changes, new technology introduction, timeline concerns, technical blockers >2 hours, major code refactoring

**Key Metrics:**
- Task completion rate (≥90%)
- QA pass rate (≥85%)
- Code review quality
- Mentoring contribution

---

#### **Junior Developer**

**Primary Responsibility:** Task execution, learning, code quality

**Daily Activities:**
- Attend 10:15 AM standup
- Work on assigned tasks (simpler features, bug fixes)
- Ask for help when stuck >30 min (Lead Dev or Senior Dev)
- Update Basecamp task status throughout the day
- Post daily update by 6:30 PM in Slack
- Log time in time tracker

**Weekly Activities:**
- Participate in Monday weekly planning (listen and learn)
- Participate in Friday weekly review

**Reports To:** Lead Developer or Senior Developer (assigned mentor)
**Reports From:** None

**Decision Authority:**
- ✅ Can decide: Implementation details for assigned tasks (within guidelines), when to ask for help
- ❌ Must escalate to Senior/Lead Dev: Any technical uncertainty, timeline concerns, task unclear, stuck >30 min, ANY code changes outside assigned task

**Key Metrics:**
- Task completion rate (≥85%)
- QA pass rate (≥80%)
- Learning progress
- Asking for help appropriately (not stuck too long)

---

#### **QA Lead / QA Engineer**

**Primary Responsibility:** Quality assurance, testing, bug reporting, ensuring deployment readiness

**Daily Activities:**
- Attend 10:15 AM standup
- Test tasks marked "Ready for QA" in Basecamp (within 24 hours)
- Report bugs with clear steps + screenshots in Basecamp
- Verify bug fixes
- Regression testing for critical features
- Post daily update by 6:30 PM in Slack
- Log time in time tracker

**Weekly Activities:**
- Monday 11:00 AM: Attend weekly planning
- Friday 6:00 PM: Attend weekly review
- Provide QA summary (bugs found, fixed, pass rate)

**Reports To:** PM (or QA Lead if structure exists)
**Reports From:** None (unless QA Lead with team)

**Decision Authority:**
- ✅ Can decide: Mark task as passed/failed, bug severity (with guidelines), when to re-test, testing approach
- ❌ Must escalate to PM: Major quality concerns, timeline impact (too many bugs), deployment concerns, conflicts with developers on bug validity

**Key Metrics:**
- Testing turnaround time (<24 hours per task)
- Bug detection rate
- Regression testing coverage
- False positive rate (bugs that aren't actually bugs)

---

#### **Designer (if applicable)**

**Primary Responsibility:** UI/UX design, client-facing design work

**Daily Activities:**
- Attend 10:15 AM standup
- Work on design tasks (mockups, wireframes, assets)
- Collaborate with developers on implementation
- Review design implementations on staging
- Post daily update by 6:30 PM in Slack
- Log time in time tracker

**Reports To:** PM
**Reports From:** None

**Decision Authority:**
- ✅ Can decide: Design approach, visual style (within brand guidelines), design tools/software
- ❌ Must escalate to PM: Client design approval, major design changes, timeline concerns

---

#### **Business Analyst (BA)**

**Primary Responsibility:** Assist PM with requirement gathering, documentation, client communication, and task creation

**Daily Activities:**
- Attend 10:15 AM standup
- Assist PM with client requirement gathering
- Document client requirements in Basecamp
- Help PM create tasks with clear acceptance criteria
- Review task descriptions for clarity before assignment
- Assist PM with client meeting preparation
- Take notes during client meetings
- Post daily update by 6:30 PM in Slack
- Log time in time tracker

**Weekly Activities:**
- Monday 11:00 AM: Attend weekly planning meeting (assist PM)
- Help PM prepare weekly client reports
- Friday 6:00 PM: Attend weekly review

**Reports To:** PM
**Reports From:** None

**Decision Authority:**
- ✅ Can decide: How to document requirements, task description format, which clarifying questions to ask
- ❌ Must escalate to PM: Client communication (always through or with PM), scope decisions, timeline commitments, any client-facing promises

**Key Responsibilities:**
- **NOT** a Project Manager - assists PM
- **DOES NOT** communicate with client independently (always with PM)
- **DOES NOT** make scope or timeline decisions
- **DOES** help clarify requirements and create clear task descriptions

**Relationship with Team:**
- Works closely with PM (reports to PM)
- Helps developers by ensuring task clarity
- May attend requirement clarification sessions with developers and PM
- Documents decisions and requirements

**Key Metrics:**
- Task clarity (% of tasks that need re-clarification)
- Requirement documentation quality
- Support to PM (time saved for PM)

---

### RACI Matrix (Who Does What for Each Process)

**Key:**
- **R** = Responsible (does the work)
- **A** = Accountable (final authority, approves)
- **C** = Consulted (provides input)
- **I** = Informed (kept in the loop)

| Process/Activity | Dev (Jr) | Dev (Sr) | Lead Dev | QA | BA | PM | Management |
|------------------|----------|----------|----------|-----|-----|-----|------------|
| **Task Assignment** | I | I | C | I | I | A | I |
| **Code Development** | R | R | C | I | - | I | - |
| **Code Review** | I | R/C | A | I | - | I | - |
| **QA Testing** | I | I | C | R/A | - | I | - |
| **Deployment to Staging** | I | R | I | I | - | I | - |
| **Deployment to Production** | I | R | C | C | - | A | I |
| **Client Communication** | - | - | I | I | R | A | C |
| **Requirement Gathering** | - | I | C | I | R | A | C |
| **Bug Fixing** | R | R | C | I | - | I | - |
| **Timeline Planning** | I | C | C | I | C | R/A | C |
| **Scope Changes** | - | I | C | I | C | R/A | A (major) |
| **Leave Approval** | - | - | I | - | - | A | A (final, via HR) |
| **Performance Review** | - | - | C | - | - | R | A |
| **Emergency Response** | I | R | R/A | C | I | A | I |
| **Project Onboarding** | I | I | C | I | R | A | C |
| **Team Onboarding** | I | C | R | I | - | A | I |

---

### Decision Ownership Summary

| Decision Type | Owner | Must Inform | Can Override |
|---------------|-------|-------------|--------------|
| Daily task prioritization | PM | Lead Dev | Management |
| Technical approach | Lead Dev | PM | Management (rare) |
| Deployment to production | PM | Lead Dev, QA | Management |
| Client communication | PM | Lead Dev (technical) | Management |
| Scope changes (minor) | PM | Lead Dev, Management | Management |
| Scope changes (major) | Management | PM, Lead Dev | - |
| Leave approval | PM (initial) + HR (final) | Team | Management |
| Hiring/Firing | Management | PM | - |
| Budget allocation | Management | PM | - |
| Code architecture | Lead Dev | PM (timeline impact) | Management (rare) |

---

### "Who Do I Go To?" Quick Reference

| I Need To... | Contact | Alternative |
|--------------|---------|-------------|
| Ask technical question | Lead Dev or Senior Dev | Peer developer |
| Report I'm stuck | Lead Dev | PM (if Lead Dev unavailable) |
| Clarify task requirements | PM | Lead Dev (if technical) |
| Report a bug | Post in Basecamp, tag developer | Notify QA Lead or PM |
| Request leave | PM (via Slack #attendance) | HR (if PM unavailable) |
| Escalate client issue | PM | Management (if urgent) |
| Report emergency (site down) | PM + Lead Dev (via #emergencies) | Management (if no response) |
| Request tool access | PM or HR | IT/Admin |
| Discuss career growth | PM | Management (annual review) |
| Report team conflict | PM (first) | HR or Management |
| Ask about billing/hours | PM | HR |

---

## 2B. Communication Channel Protocol

**Purpose:** Define exactly when to use which communication tool, what goes where, and what's client-visible vs internal-only. Eliminates confusion about "Should I post this in Slack or Basecamp?"

---

### Communication Tools & Their Purpose

| Tool | Purpose | Visibility | Speed |
|------|---------|------------|-------|
| **Basecamp** | Project tasks, client communication, project documentation | Client-visible (unless Campfire) | Not urgent (4-24 hrs response) |
| **Slack** | Internal team communication, daily updates, quick questions | Internal-only | Fast (within hours) |
| **Email** | External communication, formal requests, contracts | External parties | Formal (24-48 hrs) |
| **WhatsApp/Phone** | Emergencies only, urgent issues | Internal-only | Immediate |
| **Meetings** | Complex discussions, planning, client calls | Per meeting type | Synchronous |

---

### When to Use BASECAMP

**✅ Use Basecamp for:**
- Task creation and tracking
- Client updates on progress
- Client questions and answers
- Meeting summaries (MOM) that client should see
- Project documentation (credentials, SOW, designs)
- Deliverables and milestone updates
- Client feedback requests
- Bug reports (client should see)

**📍 Where in Basecamp:**
- **To-Do Lists:** All tasks
- **Message Board:** Client communication, MOMs, announcements
- **Docs & Files:** Credentials, contracts, designs, documentation
- **Campfire (Internal):** Team discussion (client doesn't see)
- **Schedule:** Meetings, deadlines, milestones

**⏰ Response Time:**
- Client messages: Within 4 hours (business hours)
- Task comments: Same day
- Urgent client issues: Within 1 hour (and notify in Slack)

**✍️ Tone in Basecamp:**
- Always professional and client-friendly
- No internal jargon or frustrations
- Positive and solution-focused
- Clear and concise

**❌ NEVER post in Basecamp (client-visible areas):**
- Internal team complaints
- "This client is difficult"
- Technical jargon without explanation
- Blame or excuses
- Uncertainty ("I don't know", "Maybe", "I think")
- Hours or budget concerns (discuss with PM privately first)

---

### When to Use SLACK

**✅ Use Slack for:**
- Daily standup updates (#dailymeeting)
- Quick technical questions
- Internal discussions (not client-visible)
- Team coordination
- Urgent notifications
- Leave requests (#attendance)
- Asking for help when stuck
- Sharing knowledge/solutions
- Emergency alerts (#emergencies)

**📍 Slack Channels:**

| Channel | Purpose | Who Posts |
|---------|---------|-----------|
| **#dailymeeting** | End-of-day progress updates | All team members (mandatory) |
| **#attendance** | Daily in/out, leave requests | All team members |
| **#emergencies** | Site down, critical bugs, urgent issues | Anyone (tag @PM @Lead-Dev) |
| **#general** | Team announcements, company updates | PM, Management |
| **#dev-questions** | Technical Q&A, code help | Developers |
| **#project-[name]** | Project-specific internal discussion | Project team members |
| **#random** | Non-work chat, team bonding | Anyone |

**⏰ Response Time:**
- Urgent/tagged messages: Within 2 hours
- General questions: Same day
- #emergencies: Within 15-30 minutes

**✍️ Tone in Slack:**
- Professional but more casual than Basecamp
- OK to use technical jargon (internal team)
- Be respectful and constructive
- OK to express concerns (constructively)

**🔔 @Mention Etiquette:**
- **@here:** Urgent, needs immediate attention from online people (use sparingly)
- **@channel:** Important but not urgent, everyone should see
- **@username:** Direct someone specific
- **Don't overuse @mentions** - read before interrupting people

---

### When to Use EMAIL

**✅ Use Email for:**
- External vendor communication
- Formal client communication (contracts, proposals)
- Communication with people not on Basecamp/Slack
- Receipts and documentation (needs to be in inbox)
- Official requests (server access, domain transfers)

**❌ Avoid Email for:**
- Internal team communication (use Slack)
- Active project updates (use Basecamp)
- Urgent issues (use Slack or phone)

---

### When to Use WHATSAPP/PHONE

**✅ Use WhatsApp/Phone for:**
- **Emergencies only:** Site down, critical bug, urgent client escalation
- Same-day emergency leave (call PM)
- Cannot reach someone via Slack and it's urgent

**❌ Don't use for:**
- Regular updates (use Slack)
- Task questions (use Basecamp or Slack)
- Non-urgent communication

**📞 Emergency Contact Protocol:**
1. Post in Slack #emergencies first (creates record)
2. If no response in 15 min → WhatsApp PM
3. If no response in 15 min → Call PM
4. If no response in 30 min total → WhatsApp/Call Management

---

### Client-Visible vs Internal-Only

| What You're Posting | Where | Visibility |
|---------------------|-------|------------|
| Task progress update | Basecamp (task comment) | ✅ Client sees |
| Bug report | Basecamp (task or message board) | ✅ Client sees |
| Meeting summary (MOM) | Basecamp (message board) | ✅ Client sees |
| Project milestone completed | Basecamp (message board) | ✅ Client sees |
| Requesting client feedback | Basecamp (message board or to-do) | ✅ Client sees |
| "I'm stuck on this task" | Slack (#dev-questions or DM Lead Dev) | ❌ Internal only |
| "Client keeps changing scope" | Slack (DM to PM) | ❌ Internal only |
| "This code is messy" | Slack or Basecamp Campfire | ❌ Internal only |
| Daily standup update | Slack (#dailymeeting) | ❌ Internal only |
| Technical discussion | Slack or Basecamp Campfire | ❌ Internal only |
| Leave request | Slack (#attendance) | ❌ Internal only |
| Team coordination | Slack | ❌ Internal only |

---

### Communication Flow Examples

#### Example 1: Found a Bug in Production
1. **Immediate:** Post in Slack #emergencies: "🚨 Bug found: [description]. Investigating now."
2. **5 min later:** Identify cause, post update in Slack
3. **After fix:** Deploy fix, test
4. **After verification:** Post in Basecamp (client-visible): "We identified and resolved [issue]. Monitoring for stability."

#### Example 2: Client Asks a Question in Basecamp
1. **Read question in Basecamp**
2. **If you know answer:** Respond directly in Basecamp (professional tone)
3. **If unsure:** Post in Slack: "@PM Client asked [question], need clarification"
4. **PM responds in Slack**
5. **You post in Basecamp** with approved answer

#### Example 3: Stuck on a Task
1. **Try yourself for 30 min max**
2. **Post in Slack #dev-questions:** "Stuck on [task]: [what I tried], [specific question]"
3. **Lead Dev responds in Slack** with guidance
4. **Update Basecamp task** (client-visible): "In progress, implementing [solution approach]"

#### Example 4: Daily End-of-Day Update
1. **6:30 PM:** Post in Slack #dailymeeting:
   ```
   ✅ Completed: [task name]
   🕓 Tomorrow: [what's next]
   🚧 Blockers: [any issues or "None"]
   ```
2. **Update Basecamp tasks:** Move completed tasks to "Done"
3. **Log time in Time Tracker**

---

### Communication Response Time Commitments

| Message Type | Tool | Response Time | Who Responds |
|--------------|------|---------------|--------------|
| Emergency (site down) | Slack #emergencies | 15-30 min | PM + Lead Dev |
| Client question | Basecamp | 4 hours (business hrs) | PM |
| Task clarification | Basecamp or Slack | Same day | PM or Lead Dev |
| Code review request | Basecamp or Slack | 24 hours | Peer developer |
| Help request (stuck) | Slack | 2 hours | Lead Dev or Senior Dev |
| Leave request | Slack #attendance | 4 hours | PM |
| General team question | Slack | Same day | Anyone who knows |

**If you can't respond within the committed time:**
- Reply with: "Got it, will respond by [specific time]"

---

### Communication Best Practices

**DO:**
- ✅ Use the right tool for the right purpose
- ✅ Keep client communication professional in Basecamp
- ✅ Tag the right people (don't spam @here)
- ✅ Use threads in Slack for conversations
- ✅ Search before asking (might be already answered)
- ✅ Be clear and specific in questions
- ✅ Provide context when asking for help

**DON'T:**
- ❌ Post internal frustrations in client-visible areas
- ❌ Use email for urgent issues
- ❌ Overuse WhatsApp/phone for non-emergencies
- ❌ Ignore tagged messages
- ❌ Post the same question in multiple channels
- ❌ Use @here/@channel unless truly urgent
- ❌ Discuss confidential matters in public channels

---

### Quick Decision Tree: "Where Should I Post This?"

```
Is it an emergency? (site down, critical bug)
    YES → Slack #emergencies + WhatsApp PM if needed
    NO ↓

Is it client-facing or client should see it?
    YES → Basecamp (Message Board or Task)
    NO ↓

Is it internal team discussion/question?
    YES → Slack (appropriate channel)
    NO ↓

Is it for external people (vendors, not on Basecamp)?
    YES → Email
```

---

### Direct Client Contact Protocol

**Scenario:** Client emails, calls, or messages you directly (bypassing PM)

**Why This Happens:**
- Client has your email from previous communication
- Client wants "quick answer"
- Client thinks it's faster to ask developer directly

**What You MUST Do:**

**1. Be Polite (Never Ignore Client)**
- Client is paying customer - always respond professionally
- Never say "I can't help you" or "That's not my job"

**2. Redirect to PM with Template Response**

**If Client Emails You:**
```
Subject: Re: [Their Subject]

Hi [Client Name],

Thank you for reaching out!

For project updates, timelines, and coordination, please contact our Project Manager [PM Name] at [PM Email].

[PM Name] has the complete project overview and can provide you with accurate information and timelines.

Best regards,
[Your Name]
```

**If Client Calls You:**
1. Be polite: "Thanks for calling! For accurate project updates, let me connect you with our PM [Name] who has the complete picture."
2. Take note of client's question
3. Tell PM immediately (Slack or call PM)
4. PM will call client back

**If Client Messages You on WhatsApp/Slack:**
```
Hi [Client],

Thanks for reaching out! For project coordination, please contact our PM [Name] at [contact]. They have the full project context and can help you best.
```

**3. Inform PM Immediately**
- Forward email to PM (or screenshot message)
- Brief note in Slack: "FYI - [Client Name] contacted me directly about [topic], redirected to you"
- PM will follow up with client

**What NEVER to Do:**
❌ Ignore client (rude and unprofessional)
❌ Give timeline estimates ("It'll be done by Friday")
❌ Promise features or changes ("Yes, we can add that")
❌ Discuss budget, scope, or pricing
❌ Make excuses ("I'm too busy", "Ask someone else")
❌ Give technical details client won't understand

**What You CAN Answer (If You Choose To):**
✅ "Yes, I received your email" - acknowledgment only
✅ "Let me check with PM and get back to you" - then inform PM
✅ Pure technical clarification if client asks (but still copy PM)

**Exception - Emergencies:**
If client reports site down or critical bug:
1. Acknowledge: "Thanks for reporting, investigating now"
2. Post in #emergencies immediately
3. Follow Section 18 (Emergency Response)
4. Keep client updated in Basecamp (PM and Lead Dev coordinate response)

**Why This Protocol Exists:**
- PM needs to track all client communication
- Prevents conflicting information to client
- Protects you from making commitments you can't keep
- Ensures client gets accurate, complete answers
- Maintains professional client relationship

**Remember:** You're helping the client by directing them to PM, not avoiding them.

---

## 3. Attendance & Leave Management

### A. Daily Attendance Policy

**Office Hours:** 10:00 AM – 7:00 PM (Monday to Friday)

**Attendance Marking:**
- All employees must mark attendance daily in the designated attendance system (or Slack `#attendance` channel if no system)
- **On arrival:** Post "In" with timestamp (by 10:15 AM)
- **On departure:** Post "Out" with timestamp (after 7:00 PM)
- **Format:** `✅ In - 10:00 AM` and `👋 Out - 7:15 PM`

**Late Arrival:**
- Arriving after 10:15 AM is considered late
- 3 late arrivals in a month = written warning
- Repeated pattern = review with HR and management

**Work From Home (WFH):**
- WFH requires PM and HR approval (requested 1 day in advance)
- Must be available on Slack during office hours
- Must attend all meetings (video on)
- Same productivity expectations as office work

---

### B. Leave Request & Approval Workflow

#### Step 1: Employee Requests Leave (At Least 1 Day in Advance)

**How to request:**
1. Post leave request in Slack `#attendance` channel
2. Format:
   ```
   📅 Leave Request
   Name: [Your Name]
   Date(s): [DD/MM/YYYY to DD/MM/YYYY]
   Type: [Casual/Sick/Annual/Emergency]
   Reason: [Brief reason]
   Backup: [Name of backup developer - if applicable]
   ```
3. Tag your PM: `@PM-Name`

**For planned leave (2+ days):**
- Request at least 3 days in advance
- Ensure handover notes in Basecamp for ongoing tasks

---

#### Step 2: PM Reviews & Provides Initial Approval

**PM checks:**
- [ ] Is this date critical for project delivery?
- [ ] Is backup coverage available?
- [ ] Are handover notes complete (for multi-day leave)?
- [ ] Is employee's leave balance available?

**PM responds in Slack (within 4 hours):**
- ✅ **Approved:** "Leave approved. Please coordinate with [Backup Name] for handover."
- ⏸️ **On Hold:** "Can we move this to [alternate dates] due to [client deadline/meeting]?"
- ❌ **Rejected:** "Unable to approve due to [critical deadline/insufficient coverage]. Let's discuss alternatives."

**PM documents:**
- PM adds note to internal tracker or sends email to HR with:
  - Employee name
  - Leave dates
  - Leave type
  - PM approval status
  - Impact on projects (if any)

---

#### Step 3: HR Reviews & Grants Final Confirmation

**HR checks:**
- [ ] Leave balance available for employee
- [ ] PM has approved
- [ ] No policy violations (e.g., exceeding annual quota)
- [ ] Leave recorded in HR system

**HR responds (within 24 hours of PM approval):**
- ✅ **Confirmed:** Post in Slack: "Leave confirmed for [Name] on [dates]. Balance remaining: [X days]"
- ❌ **Rejected:** "Insufficient leave balance. You have [X] days remaining. Please coordinate with PM for unpaid leave if needed."

**HR documents:**
- Update employee leave balance
- Add to company calendar
- Notify accounting (for payroll, if unpaid)

---

#### Step 4: Employee Handover (Before Leave Starts)

**Employee must:**
- [ ] Update all Basecamp tasks with current status
- [ ] Post handover notes in relevant Basecamp projects
- [ ] Brief backup developer/colleague
- [ ] Set Slack status: "🏖️ On Leave [dates]"
- [ ] Add out-of-office message if using email

---

### C. Leave Types & Allowances

| Leave Type | Annual Allowance | Advance Notice | Approval Required | Notes |
|------------|------------------|----------------|-------------------|-------|
| **Casual Leave** | 12 days | 1 day | PM (initial) → HR (final) | For personal reasons |
| **Sick Leave** | 10 days | Same day (if genuine emergency) | PM (initial) → HR (final) | Medical certificate needed for 3+ consecutive days |
| **Emergency Leave** | As needed | Same day | PM (initial) → HR (final) | Genuine emergencies only, case-by-case |
| **Unpaid Leave** | As approved | 7 days | PM → HR → Management | When leave balance exhausted |
| **Paternity/Maternity** | As per company policy | 30 days | HR → Management | Separate from annual quota |

**Leave Balance:**
- Tracked by HR
- Employees can check balance by messaging HR
- Reset annually on [January 1st / hire date anniversary - specify]

**Carry Forward Policy:**
- Casual/Sick leave: Cannot be carried forward (use it or lose it)

---

### D. Special Cases

#### Half-Day Leave
- Post in `#attendance`: "Half-day leave - [Morning/Afternoon] on [date]"
- Requires PM approval (HR confirmation not mandatory for half-days)
- Deducted as 0.5 days from leave balance

#### Same-Day Emergency Leave
- Call/WhatsApp PM immediately (don't just message in Slack)
- Post in `#attendance` as soon as possible
- Must provide explanation when back
- If sick for 3+ days: Medical certificate required

#### Extended Leave (More than 5 consecutive days)
- Requires 15 days advance notice
- Must have detailed handover plan
- PM + HR + Management approval required
- May require backup training before leave starts

#### Leave During Critical Project Phase
- PM may request to reschedule if during critical client deadline
- If unavoidable (medical/emergency), backup must be fully briefed
- Daily check-ins with backup may be requested (for emergencies only)

---

### E. Leave Rejection & Appeals

**If PM rejects leave request:**
- PM must provide clear reason (client deadline, no backup, etc.)
- PM should suggest alternative dates
- Employee can discuss with PM to find solution

**If HR rejects (insufficient balance):**
- Employee can request unpaid leave through PM → HR → Management
- Or reschedule to later when balance replenishes

**Appeals:**
- If employee disagrees with rejection, can escalate to Management
- Management makes final decision within 48 hours

---

### F. Attendance & Leave in Performance Reviews

**Attendance tracked in monthly reviews:**
- **Excellent (5/5):** No absences, always on time, zero unauthorized leave
- **Strong (4/5):** 1-2 late arrivals, all leaves properly approved
- **Satisfactory (3/5):** 3-5 late arrivals, occasional last-minute leave
- **Needs Improvement (2/5):** Frequent tardiness, pattern of unapproved absences
- **Unsatisfactory (1/5):** Multiple unapproved absences, chronic lateness

**Consequences of poor attendance:**
- 3+ unapproved absences in a month → Written warning
- Repeated pattern → 30-day PIP (Performance Improvement Plan)
- No improvement after PIP → Employment review

---

### G. Public Holidays & Company Offs

**Public holidays:**
- As per [country/state calendar - specify]
- Announced by HR at start of year
- Added to company calendar

**Company declared offs:**
- Announced at least 1 week in advance
- These do NOT count against leave balance

---

### H. Quick Reference - Leave Workflow

```
Employee requests leave (Slack #attendance)
           ↓
PM reviews (within 4 hours)
           ↓
PM approves/rejects
           ↓
    [If Approved]
           ↓
PM notifies HR with recommendation
           ↓
HR checks leave balance
           ↓
HR grants final confirmation (within 24 hours)
           ↓
Employee does handover before leave
           ↓
Leave taken
           ↓
HR updates leave balance
```

**Remember:** Leave is not final until HR confirms. Plan accordingly.

---

## 4. Task & Deadline System (Manual Tracking)

- All tasks are assigned in Basecamp with clear **titles, deadlines, descriptions, and assigned developers**.  
- Each task must include:
  - Start Date & End Date  
  - Priority (High/Medium/Low)  
  - Backup Developer  

**Daily Accountability:** Developers must post end-of-day updates in Slack's `#dailymeeting` channel.

```
✅ What was completed today
🕓 What will be done tomorrow
🚧 Any blockers or dependencies
```

---

## 4A. Task Assignment & Pickup Protocol

**Purpose:** Define exactly how tasks get assigned, prioritized, and picked up. Eliminates confusion about "Which task should I work on?" and ensures even workload distribution.

---

### How Tasks Get Created

**PM is responsible for creating tasks in Basecamp based on:**
- Client requests
- Project roadmap/milestones
- Bug reports from QA or client
- Technical debt backlog
- Scope of Work (SOW) deliverables

**Task Creation Requirements:**
Every task in Basecamp MUST include:
- ✅ **Clear title** (action-oriented, e.g., "Fix checkout bug" not "Checkout")
- ✅ **Detailed description** (what needs to be done, acceptance criteria)
- ✅ **Start date & deadline**
- ✅ **Priority** (High/Medium/Low - see below)
- ✅ **Assigned to** (specific developer or "Unassigned")
- ✅ **Backup developer** (for coverage)
- ✅ **Project/client** (which project this belongs to)

---

### Task Priority Levels

| Priority | Definition | Examples | Response Time |
|----------|------------|----------|---------------|
| **🔴 High (P0)** | Critical, blocks client/production, urgent | Site down, critical bug, client blocker, deadline today/tomorrow | Start immediately (within 1 hour) |
| **🟠 Medium (P1)** | Important, deadline within this week | Feature delivery this week, scheduled deployment, client meeting deliverable | Start within 4 hours, complete by deadline |
| **🟢 Low (P2)** | Normal priority, deadline next week or later | Regular features, minor improvements, documentation | Start within 24 hours, complete by deadline |

**PM sets priority based on:**
- Client urgency
- Project timeline
- Dependencies (other tasks waiting)
- Business impact

---

### How Tasks Get Assigned

#### Method 1: PM Assigns Directly (Default for most tasks)

**When PM assigns:**
- Complex or critical tasks (High priority)
- Tasks requiring specific expertise
- Tasks with tight deadlines
- Client-sensitive work

**Process:**
1. PM creates task in Basecamp
2. PM assigns to specific developer (considers workload, skills, availability)
3. PM tags developer in task: "@DeveloperName - assigned to you, please review and confirm"
4. Developer acknowledges in Basecamp within 2 hours: "Got it, starting [today/tomorrow]"
5. Developer updates task status: "To Do" → "In Progress"

---

#### Method 2: Self-Assignment (For experienced developers, when PM allows)

**When developers can self-assign:**
- PM posts task as "Unassigned"
- PM announces in Slack #dev-questions: "Task available for pickup: [link]"
- Developer can claim it if they have capacity

**Process:**
1. Developer checks their current workload (must have <3 active tasks)
2. Developer claims in Basecamp: "I'll take this task" (and assigns to self)
3. Developer notifies PM in Slack: "Picked up task: [task name]"
4. Developer updates task status: "To Do" → "In Progress"

**Rules for self-assignment:**
- ✅ Only if you have capacity (<3 active tasks)
- ✅ Only if you have required skills
- ✅ Only if no higher priority tasks pending
- ❌ Can't pick tasks above your skill level without approval
- ❌ Can't pick if you're already on tight deadline

---

### Task Prioritization Rules: "Which Task Do I Work On First?"

**If you have multiple assigned tasks, work in this order:**

1. **First:** 🔴 **High priority (P0)** - urgent/critical
2. **Second:** Tasks with **deadline today or tomorrow**
3. **Third:** 🟠 **Medium priority (P1)** - important this week
4. **Fourth:** **Blocked tasks** (where you're waiting on something - follow up)
5. **Fifth:** 🟢 **Low priority (P2)** - normal work

**If still unsure, ask PM in Slack:** "I have 3 tasks with same priority/deadline. Which one first?"

---

### Workload Balancing

**PM monitors workload daily:**
- Each developer should have 2-4 active tasks at a time
- No developer should have >5 active tasks (overloaded)
- No developer should have <1 task (underutilized)

**If overloaded (>5 tasks):**
- Developer notifies PM in Slack: "@PM I'm overloaded with [X] tasks. Need help prioritizing or redistributing."
- PM reviews and either:
  - Reprioritizes (moves some to Low or postpones)
  - Reassigns some tasks to other developers
  - Adjusts deadlines

**If underutilized (<1 task):**
- Developer proactively asks in Slack: "@PM I've completed my tasks. Any new assignments?"
- PM assigns next priority task
- Or developer works on: Documentation, learning, helping QA, code refactoring (see below)

---

### What to Do When You Have No Tasks

**If you complete all assigned work and no new tasks are available:**

**Option 1: Ask PM for work** (Primary)
- Post in Slack #dailymeeting or DM PM: "Completed all tasks. Ready for next assignment."
- PM will assign next task

**Option 2: Productive idle time** (If PM says no urgent tasks)
Choose from approved activities:
- ✅ **Documentation:** Update README, code comments, Basecamp project notes
- ✅ **Code review:** Help with pending peer reviews
- ✅ **Refactoring:** Improve code quality (get approval from Lead Dev first)
- ✅ **Learning:** Study new tech relevant to current projects
- ✅ **Help QA:** Assist with testing or bug reproduction
- ✅ **Optimization:** Improve performance of existing features (get approval first)
- ✅ **Proactive bug fixes:** Fix small bugs you noticed (update Basecamp)

**Log all activities in time tracker** with clear description.

**❌ Don't just sit idle** - proactively find valuable work.

---

### Task Handover (When You're Blocked or Going on Leave)

#### When Blocked on a Task

**If you can't proceed due to blocker:**
1. Update Basecamp task status: "Blocked"
2. Add comment in Basecamp: "Blocked because: [reason]. Waiting on: [client/approval/dependency]"
3. Notify PM in Slack: "@PM Task [name] blocked: [reason]"
4. Move to next task while waiting
5. Follow up daily: "Still waiting on [blocker]?"

---

#### When Going on Leave

**Before leave, handover your active tasks:**
1. Update all task statuses in Basecamp
2. Add detailed notes: "Current status: [what's done, what's pending, any gotchas]"
3. Notify backup developer: Slack DM with context
4. Notify PM: "Tasks handed over to [Backup] for my leave [dates]"
5. Backup developer reviews and confirms understanding

---

### Task Status Workflow in Basecamp

**Use these statuses in Basecamp (customize based on your Basecamp setup):**

1. **To Do** - Task created, not started yet
2. **In Progress** - Actively working on it
3. **Peer Review** - Code done, needs code review (tag reviewer)
4. **Ready for QA** - Code reviewed and merged to staging, needs testing
5. **QA Failed** - Bugs found, back to developer (include bug details)
6. **Ready for Deployment** - QA passed, waiting PM approval to deploy
7. **Deployed** - Live on production, monitoring
8. **Done** - Fully complete, client approved (archive)
9. **Blocked** - Can't proceed, waiting on external dependency

**Developer updates status as they progress** - keep it current throughout the day.

---

### Daily Task Management Routine

**Morning (10:00 AM - 10:30 AM):**
1. Check Basecamp for newly assigned tasks
2. Review your active tasks and priorities
3. Attend standup (10:15 AM)
4. If unclear on priorities, ask PM after standup

**During Day:**
- Work on highest priority task
- Update Basecamp task status as you progress
- If stuck >30 min, ask for help (don't waste time)
- Log time in time tracker

**End of Day (6:30 PM):**
1. Update all Basecamp tasks with current status
2. Post daily update in Slack #dailymeeting
3. Log time in tracker
4. Plan tomorrow's priorities

---

### Task Assignment FAQs

**Q: Can I switch tasks mid-way if I find something more urgent?**
A: Only with PM approval. Post in Slack: "@PM Found urgent issue: [X]. Should I pause current task?" PM decides.

**Q: Client asked me directly to do something. Do I just do it?**
A: No. Tell PM first. PM creates task and prioritizes. Never take direct client requests without PM approval.

**Q: I think this task will take longer than the deadline. What do I do?**
A: Notify PM immediately (don't wait till deadline). PM will either adjust timeline, reduce scope, or get help.

**Q: Two tasks have same priority and deadline. Which first?**
A: Ask PM in Slack to prioritize. PM will decide based on project needs.

**Q: Can I work on tasks from different projects simultaneously?**
A: Yes, but focus on one task at a time. Complete or reach a checkpoint before switching projects.

**Q: What if I finish a task ahead of deadline?**
A: Great! Mark it complete, notify PM, ask for next task. Don't sit idle.

---

### Requirement Clarification: What Questions to Ask

**When a task is unclear or vague, use these template questions to get clarity from PM:**

---

#### When Task Description is Vague

**Task says:** "Add user management"

**Ask PM:**
- What exactly should users be able to do? (Create, edit, delete users? Assign roles?)
- Who can access this feature? (Admin only? All users?)
- What user information should we collect? (Name, email, role, photo?)
- Should users be able to reset passwords themselves?
- Any specific design/layout required or should I follow existing patterns?
- Should there be email notifications (e.g., welcome email)?

---

#### When Requirements are Missing

**Questions to always ask if not specified:**

**Functionality:**
- What should happen when [action]? (e.g., "What happens when user clicks Submit?")
- Should this work for logged-in users only or guests too?
- Any specific validations? (e.g., email format, password strength, field limits)
- What error messages should be shown?
- Should data be saved immediately or only on Submit?

**Permissions/Access:**
- Who can see this feature? (All users? Specific roles?)
- Who can edit/delete? (Creator only? Admin only?)
- Any permission checks needed?

**Design/UI:**
- Is there a design mockup? If not, should I follow existing site patterns?
- Where should this appear? (New page? Existing page section?)
- Mobile responsive requirements?
- Any specific colors, fonts, or styling?

**Performance/Limits:**
- Any size limits? (File uploads: max size? Image dimensions?)
- Any quantity limits? (Max users per account? Max items in cart?)
- Pagination needed? (If displaying lists)
- Expected load? (10 users or 10,000 users?)

**Integration/Dependencies:**
- Does this integrate with any third-party service? (APIs, payment gateways, etc.)
- Does this depend on other features being done first?
- Any existing code/functions I should reuse?

---

#### When Client Request is Ambiguous

**Client says:** "Make it faster"

**Ask PM to clarify with client:**
- What specifically is slow? (Page load? Form submission? Search results?)
- How slow is it now? (Seconds? Minutes?)
- What's the acceptable speed? (Target: <2 seconds?)
- Does this happen always or only sometimes?
- On which browsers/devices is it slow?

---

**Client says:** "Fix the design"

**Ask PM:**
- What specifically needs fixing? (Colors? Layout? Spacing? Alignment?)
- Is there a reference design or just general improvements?
- What's wrong with current design? (Hard to read? Doesn't match brand?)
- Any specific pages or site-wide?

---

**Client says:** "Add security"

**Ask PM:**
- What security concerns? (Login? Data encryption? SSL?)
- Any specific requirements? (GDPR compliance? Two-factor auth?)
- What needs to be secured? (User data? Payment info? Admin access?)

---

#### Template for Asking Clarification

**Use this format in Basecamp:**

```
@PM - Need clarification on [Task Name]:

Current task description:
"[Copy-paste task description]"

Questions:
1. [Specific question about functionality]
2. [Specific question about design/UI]
3. [Specific question about who can access]
4. [Specific question about validations/limits]

Please clarify so I can start work on this task.

Thanks!
```

---

#### Good vs Bad Questions

**❌ Bad (too vague):**
- "What should I do?"
- "This doesn't make sense"
- "Need more info"

**✅ Good (specific):**
- "Should the 'Delete User' button be visible to all admins or only the super admin?"
- "When user uploads a photo, what's the maximum file size allowed?"
- "Should the form validate on blur or only on submit?"

---

#### When to Ask vs When to Decide

**Ask PM if:**
- Affects functionality (what feature does)
- Affects user experience (how it works)
- Affects scope (adding/removing features)
- Ambiguous or multiple valid interpretations
- Client-facing decisions (design, messaging, flow)

**You can decide if:**
- Implementation details (which function to use)
- Code structure (how to organize code)
- Variable naming
- Minor UI details within established design system
- Performance optimizations (as long as functionality unchanged)

**When in doubt, ask!** 30 seconds to ask = saves hours of rework.

---

## 4B. Time Tracking & Billing Protocol

**Purpose:** Define what's billable vs non-billable so developers log time accurately. Ensures correct client billing and transparent time reports.

---

### Billable vs Non-Billable Activities

| Activity | Billable? | Log As | Notes |
|----------|-----------|--------|-------|
| **Working on client tasks** | ✅ Yes | "Task: [Task name]" | Core billable work |
| **Client meetings** | ✅ Yes | "Client meeting - [Project]" | Include prep time |
| **Bug fixing (client's bugs)** | ✅ Yes | "Bug fix: [Description]" | Bugs in delivered work |
| **Code review (client tasks)** | ✅ Yes | "Code review - [Task name]" | Quality assurance for client work |
| **QA testing (client features)** | ✅ Yes | "QA testing - [Task name]" | Testing client deliverables |
| **Deployment to client site** | ✅ Yes | "Deployment - [Project]" | Pushing to production |
| **Client requirement clarification** | ✅ Yes | "Requirements clarification" | Understanding what to build |
| **Documentation (client project)** | ✅ Yes | "Documentation - [Feature]" | User guides, API docs for client |
| **Research for client task** | ✅ Yes (if significant) | "Research - [Topic] for [Task]" | Only if directly for task, max 1-2 hrs |
| **Rework due to unclear requirements** | ✅ Yes (usually) | "Rework - [Task]" | If PM approved vague requirements |
| | | | |
| **Fixing your own bugs** | ❌ No | Don't log | Bugs you introduced, not client's fault |
| **Internal team meetings** | ❌ No | Don't log | Daily standup, weekly review |
| **Learning new technology** | ❌ No | Don't log | Self-improvement time |
| **Code refactoring (not requested)** | ❌ No | Don't log | Unless PM specifically asked |
| **Setting up local environment** | ❌ No | Don't log | Your setup, not client work |
| **Reading Slack/email** | ❌ No | Don't log | General communication |
| **Helping colleague (non-billable)** | ❌ No | Don't log | Unless it's billable client work |
| **Rework due to your mistake** | ❌ No | Don't log | If you misunderstood clear requirements |
| **Idle time / waiting** | ❌ No | Don't log | Waiting for builds, downloads, etc. |
| **Training/onboarding** | ❌ No | Don't log | Learning company processes |

---

### How to Log Time

**Use the Time Tracker tool (specified in Section 2).**

**Format for time entries:**

**Good examples:**
```
✅ "Task: Add user profile export feature" - 3.5 hrs
✅ "Bug fix: Checkout button not working on mobile" - 1.2 hrs
✅ "Client meeting - Project XYZ weekly sync" - 0.5 hrs
✅ "QA testing - Payment gateway integration" - 2 hrs
✅ "Code review - User authentication module" - 0.75 hrs
```

**Bad examples:**
```
❌ "Work" - (too vague)
❌ "Stuff" - (meaningless)
❌ "8 hours" - (no description)
❌ "Debugging" - (what were you debugging?)
```

---

### Time Logging Rules

**1. Log daily, not weekly**
- Log time at end of each day (6:30 PM with daily update)
- Don't wait till Friday to remember what you did Monday

**2. Be honest and accurate**
- Round to nearest 0.25 hours (15 min increments)
- If task took 1 hour 10 min → log 1.25 hrs
- Don't inflate hours
- Don't underreport hours

**3. Log only actual work time**
- Breaks, lunch → don't log
- Distractions, personal calls → don't log
- Actual focused work → log

**4. One entry per task/activity**
- Don't combine multiple tasks into one time entry
- Separate entries for: task work, meetings, bug fixes, reviews

**5. Include enough detail**
- Client/PM should understand what you worked on
- Format: "[Activity type]: [Description]"

---

### When Budget is Running Low

**PM tracks hours per project** against allocated budget.

**If PM warns: "We're at 90% of budgeted hours"**

**As developer:**
- [ ] Review your tasks - are they scoped correctly?
- [ ] Flag to PM if remaining work will exceed budget
- [ ] Don't just stop logging time (that's dishonest)
- [ ] Let PM decide: reduce scope, extend budget, or prioritize

**Never:**
- ❌ Stop logging hours to "save budget"
- ❌ Log billable hours as non-billable to hide overrun
- ❌ Work unpaid overtime without PM knowledge

**PM's job:** Manage budget and scope, not yours.

---

### Special Cases

#### Rework / Multiple Attempts

**Scenario:** You built feature wrong, need to rebuild.

**If unclear requirements (PM's responsibility):**
- ✅ Billable - Log as "Rework - [Task] - clarified requirements"

**If you misunderstood clear requirements:**
- ❌ Not billable - Your mistake, don't charge client

**When unsure:** Ask PM before logging.

---

#### Research Time

**Scenario:** Need to research how to implement feature.

**Reasonable research (1-2 hours):**
- ✅ Billable - "Research - [Topic] for [Task]"

**Extensive research (>2 hours) or learning new tech:**
- ❌ Not billable - You're learning, not building
- Exception: If PM specifically asks you to research and report findings → Billable

---

#### Meetings

**Client meetings / demos:**
- ✅ Billable - Include travel time if in-person

**Internal team meetings:**
- ❌ Not billable - Standup, weekly review, retrospectives

**Meeting prep time (for client meeting):**
- ✅ Billable - Preparing demo, gathering data for client

---

### Time Approval Process

**Weekly time review:**
1. **Developer** logs time daily
2. **PM** reviews weekly (Friday or Monday)
3. **PM** approves or questions entries
4. **PM** sends time report to client (if required by contract)

**If PM questions an entry:**
- PM: "Can you clarify this 4-hour entry on Wednesday?"
- You: Explain what you did
- PM: Approves or asks to adjust

**Be prepared to explain your time entries.**

---

### Monthly Time Report (PM Sends to Client)

**Typical format:**

```
Project: [Name]
Period: [Month Year]

Total Hours: 45.5 hrs
Budget Used: 45.5 / 80 hrs (57%)

Breakdown by Activity:
- Feature development: 32 hrs
- Bug fixing: 8 hrs
- Client meetings: 2.5 hrs
- QA/Testing: 3 hrs

Detailed entries: [Attached spreadsheet]

Next month estimate: 30-35 hrs
```

**Developers should know:** Your time entries become the client report. Log professionally.

---

### Time Tracking FAQs

**Q: Do I log time for fixing bugs I created?**
A: No, if you introduced the bug. Yes, if it's a bug in previously delivered/accepted work.

**Q: Do I log time for daily standup?**
A: No, internal meetings are not billable.

**Q: Client asked me a quick question in Basecamp, 5 minutes. Log it?**
A: Yes, round to 0.25 hrs (15 min minimum). It's client communication.

**Q: I spent 3 hours learning React for this task. Billable?**
A: No, learning is not billable. Only the actual task work is billable.

**Q: I worked 10 hours but budgeted was 8. Do I log 8 or 10?**
A: Log actual 10 hours. PM will handle budget discussion with client.

**Q: I made a mistake and had to redo 2 hours of work. Log both attempts?**
A: No, log only the correct final time. Don't charge client for your mistakes.

**Q: Do I log time for code review I perform for colleague's work?**
A: Yes, if it's for client work (billable project). No, if it's internal/practice.

---

### Key Principle

**Always ask yourself:** *"Is the client getting value from this time?"*

- **Yes** → Billable
- **No / Unsure** → Ask PM before logging

**When in doubt, ask PM.** Better to clarify than log incorrectly.

---

## 5. Strict Deadline Enforcement

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

## 6. Handling Absences & Backup Coverage

- Every project has a **Primary Developer** and **Backup Developer** in Basecamp.  
- If the primary is absent, the backup takes over after PM confirmation.  
- PM ensures Basecamp handover notes are always current.

---

## 7. Managing Client Workload Variations

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

## 8. Meeting Structure & Minutes of Meeting (MOM) Format

### Meeting Overview

| Meeting | Frequency | Attendees | Duration | Purpose |
|----------|------------|------------|----------|---------|
| **Daily Standup** | Daily (10:15 AM) | All Devs + PM + QA | 15 min | Individual blockers & daily tasks |
| **Monday Weekly Planning** | Monday (11:00 AM) | PM + Leads + QA | 30-45 min | PROJECT-level planning for the week |
| **Friday Weekly Review** | Friday (6:00 PM) | PM + Leads + QA | 45-50 min | PROJECT-level progress review |
| **Client Meeting** | Weekly (3-6 PM) | PM + Assigned Dev | 30-60 min | Client progress & feedback |

---

### A. Monday Weekly Planning Meeting (11:00 AM - 11:45 AM)

**Purpose:** Plan the week ahead at PROJECT level, NOT individual task level.

**Focus:** What projects are we working on? What are project goals this week? Where might we get stuck?

---

#### Monday Meeting Agenda (PROJECT-Focused)

**For EACH Active Project (5-10 min per project):**

1. **Project Status Overview**
   - Where are we in the overall timeline?
   - What phase are we in? (Planning/Development/QA/Deployment)

2. **This Week's Goals**
   - What do we aim to complete by Friday for THIS project?
   - What milestones or deliverables are due?

3. **Task Pipeline Review**
   - How many tasks total in this project?
   - How many pending/in-progress/completed?
   - Any tasks stuck for 3+ days?

4. **Roadblocks & Dependencies**
   - What's blocking progress on this project?
   - Waiting on client? Waiting on approval? Technical issues?
   - Dependencies on other projects or team members?

5. **Resource Allocation**
   - Is the team capacity sufficient for this project this week?
   - Do we need to redistribute work?

6. **Upcoming Work Preview**
   - What's coming next week or next phase?
   - Do we need to prepare anything in advance?

---

#### Monday Meeting MOM Template

**Post this in Basecamp after the meeting (in each project's Message Board):**

```
📅 Monday Weekly Planning Meeting - [Date]
Project: [Project Name]
Attendees: [PM, Lead Dev, QA, etc.]

---

## Project Status
Current Phase: [Planning/Development/QA/Deployment]
Overall Progress: [X]% complete
Timeline Status: [On Track / At Risk / Delayed]

---

## This Week's Goals (Target for Friday)
✅ [Goal 1 - e.g., Complete user authentication module]
✅ [Goal 2 - e.g., Deploy payment gateway to staging]
✅ [Goal 3 - e.g., Client review of homepage design]

---

## Task Pipeline Overview
- Total Tasks: [X]
- Completed: [X] | In Progress: [X] | Pending: [X]
- Stuck Tasks (3+ days): [List any stuck tasks]

---

## Roadblocks & Dependencies
🚧 [Roadblock 1 - e.g., Waiting for client to provide logo files]
   → Owner: PM | ETA: [Date]

🚧 [Roadblock 2 - e.g., API integration pending third-party approval]
   → Owner: Lead Dev | ETA: [Date]

🔗 Dependencies:
   - [Dependency 1 - e.g., Need Project A completion before starting Project B Feature X]

---

## Resource Allocation This Week
- Primary Team: [Developer names assigned to this project]
- Backup: [Backup developer name]
- Estimated Hours This Week: [X hours]

---

## Upcoming Work (Next Week Preview)
📋 [What's planned for next week]
📋 [Any preparation needed now]

---

## Action Items
- [ ] [Action 1 - e.g., PM to follow up with client on logo by Tuesday]
- [ ] [Action 2 - e.g., Lead Dev to evaluate API alternatives by Wednesday]

---

Next Review: Friday 6:00 PM
```

---

#### What NOT to Discuss in Monday Meeting

❌ **Individual task assignments** (that's in daily standup)
❌ **Who is working on which specific task** (already decided)
❌ **Code-level details** (discuss offline or in peer review)
❌ **Client communication details** (PM handles separately)

**Focus:** PROJECT health, not individual task tracking.

---

### B. Friday Weekly Review Meeting (6:00 PM - 6:50 PM)

**Purpose:** Review the week's PROJECT-level progress, NOT individual performance.

**Focus:** Did we achieve project goals? What slowed us down? What's the plan for next week?

---

#### Friday Meeting Agenda (PROJECT-Focused)

**For EACH Active Project (5-10 min per project):**

1. **Week's Goals Review**
   - Did we achieve Monday's goals for this project?
   - If not, why? What blocked us?

2. **Tasks Completed vs Planned**
   - How many tasks were completed this week?
   - How many are still pending?
   - Any tasks that took longer than expected?

3. **Project Timeline Check**
   - Are we still on track for final deadline?
   - Do we need to adjust timeline or scope?

4. **Roadblocks Resolved/Outstanding**
   - Which roadblocks from Monday were resolved?
   - Which are still blocking us?
   - New roadblocks discovered this week?

5. **Quality & Client Feedback**
   - Any bugs or QA issues this week?
   - Client feedback received?
   - Client satisfaction level?

6. **Next Week Preview**
   - What are next week's project goals?
   - Any concerns or risks for next week?

---

#### Friday Meeting MOM Template

**Post this in Basecamp after the meeting (in each project's Message Board):**

```
📊 Friday Weekly Review - [Date]
Project: [Project Name]
Attendees: [PM, Lead Dev, QA, etc.]

---

## Week's Goals - Achievement Status

| Goal | Status | Notes |
|------|--------|-------|
| [Goal 1 from Monday] | ✅ Completed / ⏸️ Partial / ❌ Not Done | [Brief reason if not completed] |
| [Goal 2 from Monday] | ✅ Completed / ⏸️ Partial / ❌ Not Done | [Brief reason if not completed] |
| [Goal 3 from Monday] | ✅ Completed / ⏸️ Partial / ❌ Not Done | [Brief reason if not completed] |

**Overall Week Achievement:** [X]% of planned goals completed

---

## Task Completion Summary
- **Planned Tasks This Week:** [X]
- **Completed:** [X] ✅
- **In Progress (rolling to next week):** [X] 🔄
- **Blocked/Stuck:** [X] 🚧

**Notable Completions This Week:**
- ✅ [Major feature/milestone completed]
- ✅ [Another achievement]

---

## Roadblocks & Issues

**Resolved This Week:**
✅ [Roadblock 1 - Resolved how]

**Still Outstanding:**
🚧 [Roadblock 1 - Status update]
   → Action: [What's being done] | Owner: [Name] | ETA: [Date]

**New Roadblocks Discovered:**
🚧 [New issue found this week]
   → Action: [Plan to resolve] | Owner: [Name] | ETA: [Date]

---

## Timeline & Progress Update
- **Project Overall Progress:** [X]% → [Y]% (this week)
- **Original Deadline:** [Date]
- **Current Status:** [On Track / At Risk / Needs Discussion]
- **Estimated Completion:** [Date]

⚠️ **Timeline Risks:** [Any concerns about meeting deadline]

---

## Quality & Client Feedback

**QA Summary:**
- Bugs Found: [X] | Bugs Fixed: [X] | Open Bugs: [X]
- QA Pass Rate: [X]%

**Client Feedback:**
- [Positive feedback received]
- [Issues or concerns raised by client]
- [Client requests for next week]

**Client Satisfaction:** 😊 Happy / 😐 Neutral / 😟 Concerned

---

## Next Week's Plan (Preview)

**Goals for Next Week:**
1. [Goal 1 for next week]
2. [Goal 2 for next week]
3. [Goal 3 for next week]

**Risks/Concerns for Next Week:**
- [Concern 1 - e.g., Team member on leave, need backup coverage]
- [Concern 2 - e.g., Waiting on client approval, may cause delay]

---

## Action Items for Next Week
- [ ] [Action 1 - Owner: Name - Due: Date]
- [ ] [Action 2 - Owner: Name - Due: Date]

---

**Team Notes:**
[Any team observations, learnings, or improvements needed]

---

Next Planning Meeting: Monday [Date] 11:00 AM
```

---

#### What NOT to Discuss in Friday Meeting

❌ **Individual performance reviews** (that's in monthly 1-on-1s with HR/Management)
❌ **Who was late or absent** (that's HR/attendance matter)
❌ **Blame for delays** (focus on solutions, not blame)
❌ **New feature discussions** (schedule separate meeting)

**Focus:** PROJECT outcomes, not individual accountability.

---

### C. Key Differences Between Meetings

| Aspect | Daily Standup | Monday Planning | Friday Review |
|--------|---------------|-----------------|----------------|
| **Focus** | Individual tasks | Project planning | Project outcomes |
| **Level** | Task-level | Project-level | Project-level |
| **Timeframe** | Today/Tomorrow | This week ahead | This week past |
| **Discussed** | My blockers | Project roadblocks | Project results |
| **Output** | Verbal sync | MOM in Basecamp | MOM in Basecamp |
| **Duration** | 15 min | 30-45 min | 45-50 min |

---

### D. MOM Documentation Rules

**PM Responsibilities:**

1. **During Meeting:**
   - Take notes on laptop/notepad
   - Capture all roadblocks, action items, decisions
   - Note who owns each action item

2. **Within 2 Hours After Meeting:**
   - Post formatted MOM in Basecamp (each project's Message Board)
   - Tag relevant team members in action items
   - Update project status if needed

3. **Next Day:**
   - Follow up on action items assigned
   - Ensure roadblocks are being addressed

**MOM Must Include:**
- ✅ Date and attendees
- ✅ Clear goals/outcomes discussed
- ✅ Roadblocks and owners
- ✅ Action items with deadlines
- ✅ Next steps

**MOM Must NOT Include:**
- ❌ Vague statements ("we'll try to finish")
- ❌ Unclear ownership ("someone should handle this")
- ❌ Missing deadlines/ETAs
- ❌ Personal opinions or complaints

---

### E. Example: PROJECT vs TASK Thinking

**❌ WRONG (Task-level thinking in weekly meeting):**
> "John is working on the login page. Sarah is fixing the header bug. Mike will do the footer tomorrow."

**✅ CORRECT (Project-level thinking):**
> "**Project: Website Redesign**
> - Overall progress: 60% complete
> - This week's goal: Complete homepage and about page (8 tasks total)
> - Completed: 5 tasks ✅
> - Roadblock: Waiting on client logo (blocking header completion)
> - Timeline: On track for Oct 30 deadline"

**Focus on PROJECT health, not individual task assignments.**

---

### F. Daily Standup Structure (10:15 AM – 10:30 AM)

**Purpose:** Quick sync on individual tasks and immediate blockers. **Task-level, not project-level.**

**Duration:** 15 minutes MAX

---

#### Daily Standup Format (Round-Robin)

Each person answers (1 minute per person):
1. ✅ **What did you complete yesterday?**
2. 🕓 **What are you working on today?**
3. 🚧 **Any blockers?**

**No detailed discussions** - If something needs more than 1 minute, schedule separate discussion after standup.

---

#### After Standup (5 minutes)

**PM addresses blockers:**
- Technical blocker → Lead Dev helps (or schedules time to help)
- Waiting on client → PM follows up with client
- Task unclear → PM clarifies immediately

**PM does 2-minute project board check:**
- Any unassigned tasks? → Assign immediately
- Any tasks without deadlines? → Add deadline now
- Any tasks stuck in "To Do" for 3+ days? → Follow up with developer

**No MOM required for daily standup** - Keep it verbal and quick.

---

### G. Meeting Documentation Summary

| Meeting | MOM Required? | Where to Post | When to Post |
|---------|---------------|---------------|--------------|
| Daily Standup | ❌ No | N/A | N/A |
| Monday Planning | ✅ Yes | Basecamp (each project) | Within 2 hours |
| Friday Review | ✅ Yes | Basecamp (each project) | Within 2 hours |
| Client Meeting | ✅ Yes | Basecamp (client-visible) | Same day |

---

## 9. Quality & Review Enforcement

Every task passes through: **Developer → Peer Review → QA → PM Approval → Client Review**.

**Code & QA Rules:**
- Follow WPCS and modular coding.
- Test locally/staging before marking done.
- Maintain proper commit messages and documentation.

---

## 9A. Decision Authority & Escalation Matrix

**Purpose:** Define exactly what decisions each role can make independently vs what requires approval/escalation. Eliminates "Do I need permission for this?" confusion and speeds up decision-making.

---

### Decision-Making Framework

**Three levels of decision authority:**

1. **✅ Autonomous** - Can decide and execute immediately without asking
2. **💬 Consult** - Should discuss with someone but can proceed if agreed
3. **🔺 Escalate** - MUST get approval before proceeding

---

### Decision Authority by Role

#### **Junior Developer**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Implementation approach (within task scope) | ✅ Autonomous | Just do it, document in code comments |
| Which CSS framework to use for styling | 💬 Consult | Ask Lead Dev, proceed if approved |
| Changing task deadline | 🔺 Escalate | Ask PM in Slack |
| Adding a new library/dependency | 🔺 Escalate | Ask Lead Dev → PM |
| Modifying database schema | 🔺 Escalate | Never do this - Ask Lead Dev |
| Responding to client directly | 🔺 Escalate | Always go through PM |
| Deploy to staging | 💬 Consult | After testing locally, with peer review |
| Deploy to production | 🔺 Escalate | Never - requires PM + Lead Dev approval |
| Taking on additional task | 💬 Consult | If have capacity, confirm with PM |
| Refactoring code (outside task) | 🔺 Escalate | Ask Lead Dev first |

**Rule of thumb for Junior Devs:** When in doubt, ask.

---

#### **Senior Developer**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Technical implementation approach | ✅ Autonomous | Use best judgment, document |
| Library/framework choice (within approved stack) | ✅ Autonomous | Use industry-standard options |
| Code refactoring (minor) | ✅ Autonomous | Document what and why |
| Deploy to staging | ✅ Autonomous | After local testing + WPCS |
| Introducing new technology | 🔺 Escalate | Discuss with Lead Dev → PM |
| Changing task architecture | 💬 Consult | Discuss with Lead Dev |
| Timeline extension request | 🔺 Escalate | Notify PM immediately |
| Database schema changes | 💬 Consult | Design with Lead Dev, PM approves |
| Deploy to production | 🔺 Escalate | Requires PM approval (Section 16) |
| Scope clarification | 🔺 Escalate | Ask PM, never assume |
| Taking on self-assigned task | 💬 Consult | If capacity available, notify PM |

**Rule of thumb for Senior Devs:** Decide on technical matters, escalate timeline/scope matters.

---

#### **Lead Developer**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Technical architecture | ✅ Autonomous | Design and document |
| Technology/framework selection | 💬 Consult | Evaluate, recommend to PM (cost/timeline impact) |
| Code review approval/rejection | ✅ Autonomous | Based on quality standards |
| Deploy to staging | ✅ Autonomous | After code review + testing |
| Deploy to production | 💬 Consult | Coordinate with PM (PM has final say) |
| Developer task assignment (technical) | ✅ Autonomous | Assign based on skills |
| Timeline estimation (technical) | ✅ Autonomous | Provide realistic estimates to PM |
| Scope reduction (technical) | 💬 Consult | Recommend to PM, PM decides |
| Hiring technical interview | 💬 Consult | Conduct interview, recommend to PM/Management |
| Emergency response (technical) | ✅ Autonomous | Fix immediately, inform PM after |
| Major refactoring | 💬 Consult | Plan, get PM approval (timeline impact) |

**Rule of thumb for Lead Dev:** Own all technical decisions, involve PM for timeline/budget/scope impact.

---

#### **QA Engineer**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Mark task as Passed/Failed | ✅ Autonomous | Based on testing criteria |
| Bug severity assignment | ✅ Autonomous | Use severity guidelines (Section 9B when added) |
| Testing approach/strategy | ✅ Autonomous | Choose best testing method |
| Request bug fix | ✅ Autonomous | Report in Basecamp with details |
| Block deployment (quality concerns) | ✅ Autonomous | Notify PM + Lead Dev immediately |
| Skip testing (due to time pressure) | 🔺 Escalate | Never - inform PM of timeline conflict |
| Approve production deployment | 💬 Consult | Provide QA sign-off to PM |
| Report client-facing bug | ✅ Autonomous | Document in Basecamp, notify PM |

**Rule of thumb for QA:** Quality decisions are yours, timeline decisions go to PM.

---

#### **Project Manager (PM)**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Task prioritization | ✅ Autonomous | Daily task management |
| Timeline adjustment (minor, <3 days) | ✅ Autonomous | Adjust and communicate to team |
| Scope changes (minor, <4 hours) | 💬 Consult | Evaluate with Lead Dev, approve if within budget |
| Scope changes (major, >4 hours) | 🔺 Escalate | Discuss with Management |
| Client communication | ✅ Autonomous | All client-facing communication |
| Leave approval (initial) | ✅ Autonomous | Approve or request alternative dates |
| Deployment to production | ✅ Autonomous | After QA + Lead Dev approval |
| Budget reallocation (within project) | ✅ Autonomous | Track and report to Management |
| Budget increase | 🔺 Escalate | Request from Management with justification |
| Contract modifications | 🔺 Escalate | Involve Management |
| Team member performance issues | 💬 Consult | Document, involve HR/Management |

**Rule of thumb for PM:** Own the project delivery, escalate business/contract/budget changes.

---

#### **Management**

| Decision Type | Authority | Process |
|---------------|-----------|---------|
| Hiring/Firing | ✅ Autonomous | With input from PM/HR |
| Salary changes | ✅ Autonomous | Annual reviews or promotions |
| Major contract terms | ✅ Autonomous | Negotiate and sign |
| Budget allocation across projects | ✅ Autonomous | Strategic planning |
| Company policies | ✅ Autonomous | Create and enforce |
| Client escalations (executive level) | ✅ Autonomous | Handle C-level relationships |

**Rule of thumb for Management:** Strategic and business decisions.

---

### Escalation Paths & Timelines

#### **Technical Issues**

```
Developer stuck on technical problem (30 min)
                ↓
        Ask Senior Dev or Lead Dev (2 hours max)
                ↓
Still blocked? → Lead Dev investigates (4 hours max)
                ↓
Can't resolve? → Lead Dev escalates to PM
                ↓
PM evaluates: External help? Scope reduction? Timeline adjustment?
                ↓
        PM decides or escalates to Management (if budget impact)
```

**Timeline:** Resolve within same day, or flag as blocker for next day.

---

#### **Timeline/Deadline Issues**

```
Developer realizes can't meet deadline
                ↓
        Notify PM immediately (don't wait till deadline!)
                ↓
PM evaluates: Extend deadline? Get help? Reduce scope?
                ↓
<3 days delay → PM decides and adjusts
>3 days delay → PM escalates to Management
                ↓
    Management approves and PM communicates to client
```

**Timeline:** Flag early (as soon as you realize), not at deadline.

---

#### **Scope/Requirement Issues**

```
Task requirements unclear or client request unclear
                ↓
        Developer → PM (immediately, don't assume)
                ↓
        PM clarifies with client (within 4 hours)
                ↓
        PM updates task in Basecamp with clarification
                ↓
        Developer proceeds with clear requirements
```

**Timeline:** Same day clarification.

---

#### **Quality Issues**

```
QA finds critical bugs (production impact)
                ↓
        QA → Developer + PM (immediately, Slack #emergencies if live)
                ↓
PM prioritizes: Fix now? Scheduled fix? Workaround?
                ↓
        Developer fixes based on priority
                ↓
        QA re-tests and verifies
                ↓
If pattern of poor quality → PM + Lead Dev review with developer
```

**Timeline:** Critical bugs <2 hours, regular bugs within 24-48 hours.

---

#### **Client Escalations**

```
Client complaint or dissatisfaction
                ↓
        Anyone who hears → PM (immediately)
                ↓
PM investigates and responds to client (within 4 hours)
                ↓
Minor issue → PM resolves
Major issue (threatens relationship) → PM escalates to Management
                ↓
        Management engages at executive level
```

**Timeline:** Acknowledge to client within 1 hour, resolution plan within 4 hours.

---

#### **Team Conflict**

```
Team member conflict or communication issue
                ↓
        Individuals try to resolve directly (preferred)
                ↓
Can't resolve? → Escalate to PM
                ↓
PM mediates and documents resolution
                ↓
Unresolved or repeated pattern → PM escalates to HR + Management
```

**Timeline:** Address within 2-3 days before it festers.

---

### When NOT to Escalate (Handle Yourself)

**You can decide these yourself:**
- ✅ Implementation details (how to write the code)
- ✅ Minor UI adjustments (button color, spacing - within design system)
- ✅ Bug fixes (for bugs you introduced)
- ✅ Code organization/structure (within your task)
- ✅ Asking colleagues for help (collaboration)
- ✅ Learning/researching solutions (during work hours)
- ✅ Tool choices (IDE, local setup, dev tools)

---

### When You MUST Escalate (Don't Decide Alone)

**Always escalate these:**
- 🔺 Scope changes (anything not in original task)
- 🔺 Timeline changes (deadline extension)
- 🔺 Client communication (never respond directly)
- 🔺 Budget concerns (hours running out)
- 🔺 Database schema changes (data loss risk)
- 🔺 Security decisions (authentication, authorization, data handling)
- 🔺 Production deployments (requires approval)
- 🔺 New technology introduction (cost/learning curve impact)
- 🔺 Task re-prioritization (what to work on when)

---

### Decision-Making Best Practices

**1. When Unsure, Ask Early**
- Don't wait till you've gone down wrong path
- Better to ask "dumb question" than waste 4 hours
- Post in Slack: "Quick question before I proceed: [question]?"

**2. Provide Context When Escalating**
- Not: "Can I extend the deadline?"
- Better: "Task will take 6 hours instead of 4 because [X]. Options: extend deadline to tomorrow, or reduce scope by removing [Y]. What would you prefer?"

**3. Suggest Solutions, Don't Just Raise Problems**
- Not: "This won't work"
- Better: "This approach has [issue]. I suggest [alternative A] or [alternative B]. Which should I pursue?"

**4. Document Decisions**
- After verbal discussion, post decision in Basecamp for record
- Example: "Discussed with @PM. Decided to [decision]. Proceeding."

**5. Escalate Early, Not at Crisis**
- Flag potential issues when you first see them
- Don't wait till deadline to say "I can't finish"
- PM can help if you escalate early, harder if you wait

---

### Common Escalation Mistakes to Avoid

❌ **Mistake 1: Assuming requirements** instead of asking PM
- Results in: Wasted work, rework, client unhappy

❌ **Mistake 2: Working past deadline silently** instead of flagging early
- Results in: Project delays, PM can't plan, client disappointed

❌ **Mistake 3: Making technical decisions that affect budget/timeline** without consulting PM
- Results in: Budget overruns, timeline miss

❌ **Mistake 4: Responding to client directly** instead of routing through PM
- Results in: Miscommunication, scope creep, client expectations misaligned

❌ **Mistake 5: Staying stuck for hours** instead of asking for help
- Results in: Wasted time, deadline miss, frustration

---

### Escalation Communication Templates

#### Template 1: Timeline Concern
```
"@PM - Timeline concern on [Task Name]:
- Original estimate: 4 hours
- Actual complexity: ~8 hours because [reason]
- Options:
  1. Extend deadline by 1 day
  2. Reduce scope: Remove [feature X]
  3. Get help from [Senior Dev]
- Recommend: Option [X]
- Awaiting your decision before proceeding."
```

#### Template 2: Technical Blocker
```
"@LeadDev - Blocked on [Task Name]:
- Issue: [technical problem]
- What I tried: [attempts 1, 2, 3]
- Stuck for: [30 min/1 hour]
- Need: [guidance/pair programming/alternative approach]
- Available now for quick call if easier to explain."
```

#### Template 3: Scope Clarification
```
"@PM - Need clarification on [Task Name]:
- Task says: [original requirement]
- Question: Should this include [X]? Or just [Y]?
- Affects timeline: [if X, then +2 hours]
- Waiting on your clarification before proceeding."
```

#### Template 4: Quality Concern
```
"@PM @LeadDev - Quality concern:
- Found: [issue/pattern]
- Impact: [client-facing/internal/technical debt]
- Risk if not addressed: [consequences]
- Recommend: [fix now/schedule for later/accept risk]
- Need decision on how to proceed."
```

---

### Quick Reference: "Who Do I Ask?"

| Question/Decision | Ask | Timeline |
|-------------------|-----|----------|
| "How do I implement this technically?" | Lead Dev or Senior Dev | 2 hours |
| "Can I extend the deadline?" | PM | Immediately |
| "Client asked me a question" | PM (never answer directly) | Within 1 hour |
| "I'm stuck on a bug" | Lead Dev or Senior Dev | After 30 min of trying |
| "Should I work on task A or B first?" | PM | Same day (morning standup) |
| "Can I use this library?" | Lead Dev | Before starting |
| "Client wants to add feature" | PM | Immediately, never commit |
| "Can I deploy to production?" | PM + Lead Dev | Before deployment |
| "I need access to tool/server" | PM or IT | Same day |
| "I have a conflict with teammate" | Try to resolve, then PM | Within 2-3 days |

---

### Technical Disagreement Resolution

**Scenario:** Lead Dev says "use approach A", but you believe "approach B" is better technically.

**Can You Challenge Technical Decisions?**
✅ **Yes** - respectful technical discussion is encouraged
❌ **No** - after Lead Dev decides, you must follow the decision

**Process:**

**Step 1: Understand First (Ask Questions)**
→ Tag Lead Dev in Basecamp or ask in Slack
→ "Can you explain why we're using approach A instead of approach B? I want to understand the reasoning."
→ Lead Dev explains technical rationale

**Step 2: Present Your Technical Case (If You Still Disagree)**

If after understanding you still believe there's a better approach:

**Format your concern:**
```
@Lead-Dev - Technical Discussion on [Task Name]

Current approach: [Approach A]
Alternative I suggest: [Approach B]

Reasons:
1. Performance: [Specific data/benchmark]
2. Maintainability: [Specific reason]
3. Best practice: [Reference/documentation]

Example: [Code snippet or technical explanation]

Happy to discuss. If you still prefer approach A after considering this, I'll proceed with it.
```

**Step 3: Lead Dev Reviews & Decides**
- Lead Dev considers both approaches
- May discuss with you or team
- Makes final decision with explanation
- **Decision is final**

**Step 4: Execute (No Matter Which Approach)**
- Follow Lead Dev's decision
- Execute professionally
- No complaints to other team members

**Step 5: Learn & Document**
- If your approach proves better later: Lead Dev updates guidelines
- If Lead Dev's approach proves better: You learned something
- Both approaches documented for future reference

---

### Key Principles for Technical Discussions

✅ **Good Technical Discussion:**
- Focus on technical merit (performance, maintainability, scalability)
- Provide evidence (benchmarks, documentation, examples)
- Respect Lead Dev's experience and accountability
- Accept final decision gracefully
- Learn from the outcome

❌ **Bad Technical Disagreement:**
- "My way is better" (without evidence)
- Arguing after decision is made
- Implementing your way anyway
- Complaining to other developers
- Taking it personally

---

### Common Scenarios

**Scenario 1:** "Lead Dev chose a library I think is outdated"
→ Ask: "Can we discuss library choice? I found [newer library] that has [specific benefits]"
→ Lead Dev considers maintainability, team familiarity, project needs
→ Decides based on full context

**Scenario 2:** "Lead Dev's code structure seems inefficient"
→ Ask first: "I see we're using structure X. Is there a reason we're not using Y?"
→ May be: compatibility, client requirement, or time constraint
→ Understand context before suggesting changes

**Scenario 3:** "I found a better approach mid-implementation"
→ Stop and ask: "While implementing, I realized approach B might work better because [reason]. Should I continue with A or switch to B?"
→ Lead Dev decides based on progress and timeline

---

### What to Do If You're Overruled

**When Lead Dev chooses the other approach:**
1. ✅ Say: "Got it, I'll proceed with approach A. Thanks for explaining."
2. ✅ Implement it professionally
3. ✅ Document any challenges for future learning
4. ✅ If it works well, acknowledge it
5. ✅ If issues arise, report objectively (not "I told you so")

**What NOT to Do:**
❌ "I disagree but whatever" (passive-aggressive)
❌ Sabotage the approach to prove you're right
❌ Keep arguing after decision made
❌ Tell other developers "Lead Dev made wrong choice"
❌ Bring it up in every meeting

---

### When to Escalate to PM (Rare)

**Only escalate if:**
- Lead Dev's decision will cause significant technical debt
- Security or compliance issue
- Will miss deadline significantly
- Violates client requirements

**How to escalate:**
```
@PM Need your input on technical decision for [Task]:

Situation: [Brief technical summary]
Lead Dev decided: [Approach A]
My concern: [Specific impact on timeline/quality/security]
Tried: [Discussed with Lead Dev, they explained reasoning]

Not questioning Lead Dev's authority, but want PM aware of [specific risk/impact]
```

**Note:** This should be extremely rare. Lead Dev has technical authority for a reason.

---

### Timeline Concern Communication

**Scenario:** PM assigns task: "Complex feature, needs to be done by EOD today."

**Can You Push Back on Deadlines?**
✅ **Yes** - if you have legitimate technical concerns
❌ **No** - not just because you don't feel like it

**When to Raise Timeline Concerns:**
- Estimate significantly exceeds deadline
- Unforeseen technical complexity
- Blockers/dependencies
- Need to maintain quality (can't rush it)

**When NOT to Raise Concerns:**
- You just don't want to work hard
- You procrastinated
- You want to work on something else
- You're trying to avoid challenging work

---

### How to Communicate Timeline Concerns

**Do This IMMEDIATELY When Task Assigned (Not Day Before Deadline)**

**Step 1: Quick Assessment (15-30 min)**
- Break task into subtasks
- Estimate each subtask
- Identify dependencies/blockers
- Calculate realistic timeline

**Step 2: Communicate to PM (Basecamp or Slack)**

**Template:**
```
@PM Timeline concern on [Task Name]:

Task assigned: [When]
Deadline requested: [Date/Time]
Estimated time needed: [X] hours

Breakdown:
- [Subtask 1]: [Y] hours
- [Subtask 2]: [Z] hours
- [Subtask 3]: [A] hours
- Testing: [B] hours

Complexity factors:
- [Reason 1: New technology/complex integration/etc.]
- [Reason 2: Dependencies on X]

Options:
1. Extend deadline to [realistic date] - maintains quality
2. Reduce scope: Remove [specific feature] - meets deadline
3. Get help from [Senior Dev] for [specific part] - shares work
4. Accept timeline with risk: May need extra time for bugs/issues

Recommendation: Option [X]

I can start immediately once we decide.
```

**Step 3: PM Responds**
PM will:
- Adjust deadline
- Reduce scope
- Assign help
- Confirm priority (maybe other tasks can wait)
- Or explain why deadline is firm (client demo, legal requirement, etc.)

**Step 4: Execute Based on PM Decision**
- If timeline adjusted: Great, proceed with quality
- If deadline firm: Do your best, keep PM updated on progress
- If getting help: Coordinate with assigned teammate

---

### If PM Insists on Unrealistic Deadline

**What to do:**
1. ✅ Acknowledge: "Understood, I'll do my best to meet it"
2. ✅ Set expectations: "Given the complexity, there's risk of bugs. I'll need extra QA time."
3. ✅ Work hard and professionally
4. ✅ Keep PM updated: Daily progress updates
5. ✅ Ask for help if truly stuck: "I'm X% done, need help with Y to meet deadline"

**What NOT to do:**
❌ Refuse: "I can't do it" (without trying)
❌ Complain: "This is impossible"
❌ Give up: Do poor quality work intentionally
❌ Blame PM later: "You gave me impossible deadline"
❌ Wait until last minute to say you can't finish

---

### Common Timeline Scenarios

**Scenario 1:** "PM says 2 hours, I think it's 8 hours"
→ Explain why: "This involves [complex integration/new feature/refactoring]"
→ Offer breakdown
→ PM decides based on priority

**Scenario 2:** "I estimated 4 hours, taking 8 hours"
→ Notify PM at 4-hour mark: "Hitting complexity, need 4 more hours"
→ PM adjusts or helps prioritize
→ Don't wait until deadline to notify

**Scenario 3:** "Multiple urgent tasks, can't finish all"
→ Ask PM: "Have task A (4h) and task B (6h), both urgent. Which first?"
→ PM prioritizes
→ Do that one first

---

### Key Principles

**Good Timeline Communication:**
✅ Communicate early (when task assigned)
✅ Provide specific estimates with reasoning
✅ Offer solutions, not just problems
✅ Be honest about your capabilities
✅ Update PM if estimates change mid-task

**Bad Timeline Communication:**
❌ Wait until deadline to say "can't finish"
❌ Just say "it's too much" without specifics
❌ Commit to impossible deadline to look good
❌ Blame PM for your poor estimation
❌ Give up without trying

**Remember:** PM is on your side. They need accurate information to manage client expectations and help you succeed.

---

## 9B. Bug Priority & Issue Handling System

**Purpose:** Define bug severity levels so everyone knows which bugs are urgent and which can wait. Eliminates confusion: "Should I drop everything to fix this bug?"

---

### Bug Severity Levels

| Priority | Name | Definition | Examples | Response Time | Who Fixes |
|----------|------|------------|----------|---------------|-----------|
| **🔴 P0** | **Critical** | Production broken, site down, data loss, security breach | Site completely down, checkout broken, user data exposed, critical security vulnerability | **Immediately** (within 30 min) | Drop everything, all hands on deck |
| **🟠 P1** | **High** | Major feature broken, significant user impact, client blocker | Login not working, dashboard error, major feature completely broken, client can't do their work | **Same day** (within 4 hours) | Prioritize over other work |
| **🟡 P2** | **Medium** | Minor bug, workaround exists, affects some users | Form validation issue (but form submits), styling broken on one page, minor feature glitch | **This week** (within 2-3 days) | Schedule between tasks |
| **🟢 P3** | **Low** | Cosmetic, nice-to-have, very minor impact | Typo, color slightly off, minor UI inconsistency, feature enhancement request | **Next sprint** (when time allows) | Backlog, low priority |

---

### How to Assign Bug Severity

**QA or whoever finds the bug assigns initial severity based on:**

1. **Is production affected?** → P0 or P1
2. **Can users still work?** → If yes: P2 or P3, If no: P0 or P1
3. **Is there a workaround?** → If yes: downgrade one level
4. **How many users affected?** → All users: higher priority, Few users: lower priority

**PM can override severity** if business impact differs.

---

### Bug Severity Examples

#### 🔴 **P0 - Critical (Fix NOW)**
- Entire site returns 500 error
- Checkout page broken (e-commerce site)
- Database connection lost
- User data being deleted accidentally
- Security vulnerability discovered
- Payment processing completely broken

**Action:** Post in Slack #emergencies, tag @PM @Lead-Dev, drop current work

---

#### 🟠 **P1 - High (Fix Today)**
- Login page broken (users can't log in)
- Dashboard showing wrong data
- Major feature completely non-functional
- API integration broken (blocking client work)
- Email notifications not sending at all
- Admin panel inaccessible

**Action:** Notify PM in Slack, prioritize fixing today

---

#### 🟡 **P2 - Medium (Fix This Week)**
- Form validation shows wrong error message (but form works)
- One page has broken styling (others are fine)
- Search doesn't work on one specific condition
- Image upload slow (but works)
- Tooltip shows wrong text
- Feature works but UX is confusing

**Action:** Add to task list, fix between other work this week

---

#### 🟢 **P3 - Low (Fix When Time Allows)**
- Button text says "Submit" instead of "Save"
- Color is #333 instead of #000 (minor visual difference)
- Spacing is 10px instead of 15px
- Nice-to-have feature enhancement
- Minor UI inconsistency that doesn't affect functionality

**Action:** Add to backlog, fix during maintenance sprint or downtime

---

### Bug Reporting Template

**When reporting a bug in Basecamp, include:**

```
🐛 Bug: [Short description]

Severity: [P0 / P1 / P2 / P3]

Environment: [Production / Staging / Local]

Steps to Reproduce:
1. Go to [URL]
2. Click on [button/link]
3. Enter [data]
4. Observe [issue]

Expected Behavior:
[What should happen]

Actual Behavior:
[What actually happens]

Screenshots/Video:
[Attach screenshot or video]

Browser/Device:
[Chrome 120 / Safari iOS / etc.]

Frequency:
[Always / Sometimes / Once]

Additional Notes:
[Any other relevant info]
```

---

### Bug Workflow

#### Step 1: Bug Discovery
- QA finds during testing → Reports in Basecamp task
- Client reports → PM creates Basecamp task
- Developer finds → Reports in Basecamp

#### Step 2: Severity Assignment
- Reporter assigns initial severity (P0/P1/P2/P3)
- PM reviews and may adjust based on business impact

#### Step 3: Bug Assignment
- **P0:** Assign immediately to developer who can fix fastest
- **P1:** Assign same day to available developer
- **P2:** Schedule into this week's work
- **P3:** Add to backlog

#### Step 4: Bug Fixing
- Developer reproduces bug
- Developer fixes and tests locally
- Developer updates Basecamp: "Fixed, ready for QA re-test"
- Code review (if significant change)

#### Step 5: QA Verification
- QA re-tests on staging
- If still broken → Back to developer with details
- If fixed → Mark as "QA Passed"

#### Step 6: Deployment
- **P0/P1:** Deploy to production ASAP after QA pass (get PM approval per Section 16)
- **P2/P3:** Deploy with next scheduled deployment

---

### Special Cases

#### Bug Found in Production (After Deployment)
1. **Assess severity** - Is it P0/P1?
2. **If P0:** Follow emergency response (Section 18)
3. **If P1:** Create hotfix branch, fix, test, deploy same day
4. **If P2/P3:** Create task, schedule normally

#### Bug vs Feature Request
**Bug:** Something that's broken or doesn't work as originally intended
**Feature Request:** New functionality that wasn't in original scope

If client says "This doesn't work" but it was never built → It's a feature request (handle via scope change Section 17)

#### Regression Bug (Broke something that was working)
- Automatically P1 or P2 (depending on impact)
- Assign to developer who made the recent change
- Review why it wasn't caught in QA

---

### Bug Priority Escalation/De-escalation

**Can escalate (increase severity) if:**
- More users affected than initially thought
- Business impact higher than expected
- Client explicitly requests urgent fix

**Can de-escalate (decrease severity) if:**
- Workaround found
- Affects fewer users than thought
- Client says it can wait

**PM has final say on severity.**

---

### Bug Metrics (PM Tracks Monthly)

- **Total bugs reported:** [X]
- **P0 bugs:** [X] (Goal: 0 per month)
- **P1 bugs:** [X] (Goal: <5 per month)
- **Bug fix time (P1):** [X hours average] (Goal: <4 hours)
- **QA pass rate:** [X%] (Goal: >85% - fewer bugs = higher quality)

---

### Bug Prevention Best Practices

**For Developers:**
- Test thoroughly locally before marking "Ready for QA"
- Run WPCS and Plugin Checker
- Test on multiple browsers (Chrome, Firefox, Safari)
- Test on mobile (responsive)
- Think about edge cases (what if user enters invalid data?)

**For QA:**
- Follow QA testing checklist (Section 21A)
- Test both happy path and error cases
- Test on multiple browsers/devices
- Regression test related features

**For PM:**
- Ensure requirements are clear (Definition of Ready - Section 21)
- Don't rush deployments
- Allow time for proper QA

---

### Quick Reference: Bug Response Times

| Severity | Acknowledge | Start Fix | Complete Fix | Deploy |
|----------|-------------|-----------|--------------|--------|
| P0 | 15 min | Immediately | 1-2 hours | ASAP |
| P1 | 1 hour | 2 hours | Same day | Same day or next |
| P2 | 4 hours | This week | 2-3 days | Next deployment |
| P3 | Same day | When time allows | Next sprint | Next maintenance |

---

## 10. Reporting & Visibility

**Daily:** Developers post updates in Slack.
**Weekly:** PM summarizes progress in Basecamp.
**Monthly:** PM and Leads conduct performance review meetings.

---

## 11. Manual Self-Driven Workflow Summary

1. PM assigns and reviews tasks in Basecamp.  
2. Developers acknowledge and update in Slack.  
3. Backup developers handle absences.  
4. Meetings reinforce accountability.  
5. PM maintains weekly and monthly reports.  

---

## 12. Frequently Asked Questions (FAQs)

### General
- **Tools Used:** Basecamp for projects, Slack for communication, Git for code.
- **Missed Updates:** Daily status must be posted by 6:45 PM.
- **Leave Policy:** Request in Slack #attendance channel (1 day advance). PM approves first, then HR grants final confirmation. See Section 3 for full details.

### Developers
- Post daily updates in Slack `#dailymeeting`.  
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

## 13. Repository, Access & Client Communication Policy

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

## 14. Performance Evaluation & HR Guidelines

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
| Communication | 100% daily updates in #dailymeeting |

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

## 15. Project Onboarding Process (Starting New Projects)

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

## 16. Deployment/Release Process (Going to Production)

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

## 17. Scope Change/Change Request Process

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

## 18. Emergency/Crisis Response

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

## 19. Git Workflow & Branching Strategy

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

## 20. New Team Member Onboarding

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

## 21. Definition of Ready & Definition of Done

**Purpose:** Define when a task is READY to start (Definition of Ready) and when it's truly COMPLETE (Definition of Done). Prevents wasted work and ensures quality.

---

### A. Definition of Ready (Before You Start Working)

**A task is READY to start when ALL of these are met:**

**Requirements & Clarity:**
- [ ] **Task description is clear** - You understand what needs to be built
- [ ] **Acceptance criteria defined** - You know how to verify it's done correctly
- [ ] **No ambiguity** - If anything is unclear, clarify with PM first (don't assume)

**Design & Assets:**
- [ ] **Designs/mockups attached** (if UI/frontend work) - You know what it should look like
- [ ] **Assets provided** (images, icons, content) - If needed

**Dependencies:**
- [ ] **No blockers** - Not waiting on client approval, other tasks, or external dependencies
- [ ] **API/integrations ready** (if task depends on them)

**Estimated & Prioritized:**
- [ ] **Deadline is set** - You know when it's due
- [ ] **Priority is clear** (High/Medium/Low) - You know its urgency

---

### What to Do if Task is NOT Ready

**Don't start working!** Instead:

1. **Comment in Basecamp:** "This task is not ready to start because [reason]"
2. **Tag PM:** "@PM Need clarification on [specific issue]"
3. **Wait for PM response** before starting
4. **Move to next task** in the meantime

**Examples of NOT Ready:**
- ❌ Task says "Add user management" (too vague - what features exactly?)
- ❌ Design mockup says "coming soon" (can't build without design)
- ❌ Task depends on API that's not built yet (blocker)
- ❌ No acceptance criteria (how do I know when it's done?)

**Don't waste time building the wrong thing!** Get clarity first.

---

### B. Definition of Done (What "Complete" Actually Means)

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

## 21A. Code Review & QA Testing Checklists

**Purpose:** Simple checklists so peer reviewers and QA know exactly what to check. Ensures consistent quality without guessing.

---

### A. Code Review Checklist (For Peer Reviewers)

**When a developer requests code review, check ALL of these:**

#### 1. Functionality
- [ ] **Does it solve the requirement?** - Read the original task, does the code do what was asked?
- [ ] **Does it work?** - Pull the branch, test it locally, does it actually work?
- [ ] **Edge cases handled?** - What if user enters invalid data? Empty fields? Wrong format?

#### 2. Code Quality
- [ ] **WPCS passes?** - Run `phpcs --standard=WordPress` - should show 0 errors
- [ ] **Plugin Checker passes?** (if plugin work) - No errors/warnings
- [ ] **Code is readable?** - Can you understand what it does without asking?
- [ ] **No duplicate code?** - DRY principle (Don't Repeat Yourself)
- [ ] **Functions/variables named clearly?** - Names make sense?

#### 3. Best Practices
- [ ] **Security checked?** - No SQL injection? Data sanitized? Escaped output?
- [ ] **Error handling present?** - What happens if API fails? Database query fails?
- [ ] **WordPress standards followed?** - Using WordPress functions (not reinventing the wheel)?
- [ ] **Comments where needed?** - Complex logic explained?

#### 4. Testing
- [ ] **No console errors?** - Check browser console
- [ ] **Responsive?** (if frontend) - Test on mobile view
- [ ] **Performance OK?** - No obvious slow queries or loops?

---

### Who Can Approve Code Reviews

**Any of these can approve code reviews:**
- ✅ Senior Developer (for junior/mid-level developer code)
- ✅ Lead Developer (for any code)

**If Multiple Reviewers Disagree:**
- Lead Developer makes final decision
- Lead Developer reviews both perspectives
- Decision is final

**Code Review Assignment:**
- PM or Lead Dev assigns reviewer when task is ready
- Or developer requests review from specific senior/lead dev
- Junior developers typically not assigned as primary reviewers (can shadow/learn)

---

### Code Review Response

**If approved:**
- Comment in Basecamp: "Code review approved ✅ Ready to merge to staging for QA"
- Approve the pull request (if using GitHub/GitLab)

**If issues found:**
- Comment in Basecamp with specific issues:
  ```
  Code review feedback:
  1. [Issue 1] - Line 45: Missing error handling for API call
  2. [Issue 2] - Function name unclear, suggest rename to getUserData()
  3. [Issue 3] - WPCS shows 3 errors on lines 78, 82, 95

  Please fix and re-request review.
  ```
- Mark task as "Needs Revision"
- Developer fixes issues and re-requests review

**Response time:** Within 24 hours of review request

---

### B. QA Testing Checklist (For QA Team)

**When testing a task marked "Ready for QA", check ALL of these:**

#### 1. Core Functionality
- [ ] **Feature works as described?** - Read task description, does it do what was requested?
- [ ] **Acceptance criteria met?** - All points in acceptance criteria are satisfied?
- [ ] **Happy path works?** - Normal usage works perfectly?
- [ ] **Error handling works?** - Invalid inputs show proper error messages?

#### 2. Browser & Device Testing
- [ ] **Chrome (desktop)** - Works correctly?
- [ ] **Firefox (desktop)** - Works correctly?
- [ ] **Safari (desktop)** - Works correctly?
- [ ] **Mobile responsive?** - Test on mobile view (Chrome DevTools or real device)
- [ ] **Tablet view?** (if applicable) - Medium screen sizes work?

#### 3. Technical Checks
- [ ] **No console errors?** - Open browser console (F12), should be clean
- [ ] **No broken images/links?** - All images load, all links work?
- [ ] **Forms work correctly?** (if form involved) - Validation works? Submission works?
- [ ] **Data saves correctly?** (if data changes) - Check database/backend

#### 4. User Experience
- [ ] **UI matches design?** (if design provided) - Colors, spacing, fonts match mockup?
- [ ] **Loading states?** (if async operations) - Shows loading spinner? No blank screens?
- [ ] **Success/error messages clear?** - User knows what happened?
- [ ] **Accessibility basics?** - Can tab through form? Contrast OK? Alt text on images?

#### 5. Regression Testing
- [ ] **Didn't break existing features?** - Test related features to ensure nothing broke
- [ ] **No side effects?** - Other pages/features still work normally?

---

### Bug Severity During Testing

Use bug priority system (Section 9B):
- **P0:** Site broken, can't test further → Report immediately in Slack
- **P1:** Major feature broken → Report in Basecamp, notify PM
- **P2:** Minor bug → Report in Basecamp
- **P3:** Cosmetic issue → Note in Basecamp

---

### QA Test Result

**If ALL checks pass:**
- Comment in Basecamp: "QA Passed ✅ Ready for deployment"
- Attach screenshots showing it works
- Change task status to "Ready for Deployment"

**If bugs found:**
- Report each bug using bug template (Section 9B)
- Comment in Basecamp:
  ```
  QA Failed ❌

  Bugs found:
  1. [P1] Login form doesn't validate email format
  2. [P2] Button alignment off on mobile
  3. [P3] Typo in success message

  Assigning back to developer for fixes.
  ```
- Change task status to "QA Failed"
- Assign back to developer

**Response time:** Test within 24 hours of "Ready for QA" status

---

### Testing Tips

**For Developers (Self-Testing Before QA):**
- Run through this QA checklist yourself BEFORE marking "Ready for QA"
- Catch obvious issues yourself → Higher QA pass rate → Less back-and-forth

**For QA:**
- Test on staging, NOT production
- Test both as logged-in user AND logged-out (if applicable)
- Try to break it (enter weird data, click rapidly, etc.)
- If unsure if something is a bug → Ask developer or PM

---

### QA Pass Rate Goal

**Target:** 85%+ pass rate (tasks that pass QA on first try)

**If pass rate <85%:**
- Developers need to test more thoroughly before QA
- Review Definition of Done checklist
- Consider pair programming for quality issues

---

### When QA and Developer Disagree on Bug Validity

**Scenario:** QA reports a bug. Developer says "That's not a bug, it's working as designed."

**Process:**

**Step 1: Developer Explains (In Basecamp Task Comment)**
```
@QA - This is not a bug because:
- According to requirement: [quote requirement]
- Expected behavior is: [explain]
- This is working as designed
```

**Step 2: QA Reviews Explanation**

**If QA agrees after explanation:**
- Mark as "Not a Bug" in Basecamp
- Close the issue
- Document for future reference

**If QA still disagrees:**
- Comment: "@Lead-Dev Can you review? QA believes this is a bug because [reason], but developer says it's working as designed."
- Tag Lead Developer for decision

**Step 3: Lead Developer Reviews**
- Checks original requirements/acceptance criteria
- Checks client expectations (asks PM if needed)
- Makes decision: **Bug or Not Bug**
- Posts decision in task with explanation
- **Decision is final**

**Step 4: If Requirements are Ambiguous**
- Lead Dev tags PM: "@PM Need client clarification: [specific question]"
- Task put on hold until clarified
- PM gets client clarification
- Then proceed with fix or mark as not a bug

**Key Principles:**
✅ Focus on requirements, not opinions
✅ Be respectful in communication
✅ Both QA and Dev want quality - same goal
✅ If in doubt, check requirements first
✅ Lead Dev is tiebreaker

**What NOT to Do:**
❌ Argue back and forth (escalate to Lead Dev after 1 exchange)
❌ Take it personally ("You always find fake bugs")
❌ Ignore QA's concern without explanation
❌ Close bug without proper review

**Common Scenarios:**

**Scenario 1:** QA says "Button alignment is off", Dev says "It matches the design"
→ Solution: Check design file, Lead Dev confirms

**Scenario 2:** QA says "Error message is confusing", Dev says "It's technically correct"
→ Solution: UX/clarity issue - Lead Dev or PM decides if worth fixing

**Scenario 3:** QA says "Feature doesn't work", Dev says "Works in my environment"
→ Solution: Environment issue - Dev investigates with QA

---

### Regression Testing Scope

**Question:** Do I test the entire application or just the changed part?

**Guidelines:**

**For Bug Fixes:**
→ Test the fixed feature thoroughly
→ Test directly related features

**Example:**
- Bug fixed: Login page
- Test: Login, Logout, Password Reset, Remember Me
- Don't need to test: Shopping cart, checkout, user profile (unrelated)

**For New Features:**
→ Test the new feature completely
→ Test integration points (how it connects to existing features)
→ Smoke test critical paths

**Example:**
- New feature: User reviews
- Test: Submit review, edit review, delete review, view reviews
- Integration: User profile (shows user's reviews), Product page (displays reviews)
- Smoke test: Users can still login, browse products, checkout (critical paths still work)

**For Major Changes (Database, Architecture, APIs):**
→ **Full regression testing required**
→ PM or Lead Dev will explicitly state: "This needs full regression testing"
→ Test all major features end-to-end

**Example:**
- Change: Database schema migration
- Test: Everything (this affects all features)

**Time Allocation:**
- Bug fix: ~2x time of original testing
- New feature: Test feature + integration (30-50% more time)
- Major change: Full regression (as estimated by Lead Dev/PM)

**If Unsure of Scope:**
→ Ask in Basecamp task: "@Lead-Dev What's the regression scope for this change?"
→ Lead Dev specifies what needs testing

**What is "Smoke Testing"?**
Quick check of critical paths to ensure nothing major broke:
- Can users login?
- Can users perform primary actions? (buy product, submit form, etc.)
- No major errors on key pages?

Time: 15-20 minutes

**Priority Order:**
1. Test the changed functionality (thoroughly)
2. Test directly related features
3. Smoke test critical paths
4. Full regression (only if specified)

---

## 21B. QA Environment & Test Data Setup

**Purpose:** Ensure QA has everything needed to test effectively

---

### Test Environments

**Staging Environment:**
- **Purpose:** QA testing before production
- **URL:** [Your staging URL - document in Basecamp Docs & Files]
- **Access:** All developers and QA have access
- **Credentials:** Stored in Basecamp → Project → Docs & Files → "Environment Credentials"
- **Updated by:** Lead Developer or PM

**Production Environment:**
- **Purpose:** Live client site
- **URL:** [Production URL]
- **Access:** View-only for QA; Lead Dev and PM can modify
- **Credentials:** Stored in Basecamp (restricted access)
- **Rule:** Never test on production unless explicitly approved by PM

**Local Development:**
- Each developer has local environment
- QA does NOT test on local (not consistent)
- Developers test locally before pushing to staging

---

### Test Accounts & Test Data

**Developer's Responsibility:**
Before marking task **"Ready for QA"**, developer MUST:

1. **Create Test Accounts** (if feature needs login/roles)
   - At least 2 test accounts with different roles (if applicable)
   - Example: Admin account, Regular user account

2. **Create Test Data**
   - Sample data that demonstrates the feature
   - Example: If testing "user can delete posts", create 3-5 sample posts

3. **Document in Task**
   - Post credentials and test data in Basecamp task comment
   - Format:
   ```
   Test Accounts:
   - Admin: username / password
   - User: username / password

   Test Data:
   - 5 sample posts created
   - Test product ID: 123
   ```

**What If Test Accounts/Data Missing:**

**QA's Action:**
1. Comment in Basecamp task: "Cannot start testing - missing test accounts/data"
2. Move task back to "In Progress" status
3. Tag developer: "@Developer Need test accounts to proceed"
4. **Do NOT** create test data yourself (developer must provide)

**Developer's Action:**
1. Create accounts/data within 2 hours
2. Document in task
3. Move back to "Ready for QA"

---

### If Staging Environment is Down

**QA Action:**
1. Check if it's actually down (ask another QA/developer)
2. Post in Slack #emergencies: "🚨 Staging down, cannot test - [describe issue]"
3. Tag Lead Developer
4. Update affected tasks: "On hold - staging down"

**Lead Developer Action:**
1. Investigate immediately (within 30 min)
2. Fix or escalate to hosting/DevOps
3. Update team in Slack when resolved
4. Inform PM if significant delay expected

**PM Action:**
1. Adjust timelines if staging down >4 hours
2. Communicate impact to client if needed

---

### Environment Credentials

**Where Stored:**
- Basecamp → [Project Name] → Docs & Files → "Environment Credentials" document

**Document Contains:**
- Staging URL and credentials
- Database access (if needed for testing)
- API keys (if applicable)
- Admin panel access
- Test payment gateway credentials

**Updated By:**
- Lead Developer (primary)
- PM (if Lead Dev unavailable)

**If Credentials Don't Work:**
1. QA notifies Lead Dev in Slack
2. Lead Dev updates credentials
3. Lead Dev posts update in #general: "Environment credentials updated"
4. Team checks credentials work

---

### Access Requests

**New Team Member Needs Access:**
1. PM or Lead Dev grants access
2. Credentials shared via Basecamp (not Slack - Slack not secure)
3. Document who has access (for security)

**Third-Party Tools (Analytics, Error Tracking):**
- PM manages access
- Request via Slack: "@PM Need access to [tool] for testing"

---

### Common QA Environment Issues

| Issue | Solution |
|-------|----------|
| **Staging is slow** | Check with Lead Dev - may be server issue |
| **Changes not reflecting on staging** | Developer may need to clear cache/deploy again |
| **Test data disappeared** | Staging DB may have been reset - ask Lead Dev |
| **Cannot login to staging** | Check credentials document, may have changed |
| **SSL certificate error** | Inform Lead Dev - certificate may have expired |
| **API errors in staging** | Check with developer - API keys may need update |

---

### Testing Best Practices

**Always Test on Staging:**
✅ Test on staging environment
✅ Use provided test accounts
✅ Document steps taken
✅ Take screenshots of issues

**Never Test on Production:**
❌ Don't test on live client site (unless PM explicitly says so)
❌ Don't use real customer data
❌ Don't create test data on production

**Environment Sync:**
- Staging should mirror production as closely as possible
- If staging looks different from production → Inform Lead Dev
- Major differences can cause bugs to slip through

---

## 22. When You're Stuck (Simple Escalation)

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

## 23. Response Time Expectations

| What | Response Time | Who Responds |
|------|---------------|--------------|
| Client question (Basecamp) | Same day (within 4 hours) | PM |
| Developer help request | Same day (within 2 hours) | PM or Lead Dev |
| Peer code review | Within 24 hours | Peer Developer |
| QA testing start | Within 24 hours of "QA Ready" | QA Team |
| Security/Critical bug | Immediately (within 30 min) | Everyone |

*If you can't meet the deadline, reply: "Got it, will respond by [time]"*

---

## 24. Document Control

- **Owner:** HR & Project Management Team
- **Version:** 9.0 - COMPLETE + OPERATIONAL EDGE CASES
- **Last Updated:** November 2025
- **Next Review:** February 2026
- **Status:** ✅ Complete - All essential sections + operational edge case handling
- **Changelog:**
  - v9.0: **OPERATIONAL COMPLETENESS - Team-Level Edge Cases:** Added 8 operational sections + fixed contradictions:
    - BA Role Definition: Business Analyst as PM assistant (requirement gathering support)
    - PM Backup Process: Who covers when PM unavailable (Lead Dev backup protocol)
    - Direct Client Contact Protocol: How to respond when client bypasses PM (templates included)
    - QA-Dev Bug Disagreement Resolution: Team-level dispute resolution (Lead Dev decides)
    - Test Environment & Data Setup (Section 21B): Who creates test accounts, staging protocols
    - Technical Disagreement Process: How to respectfully challenge Lead Dev decisions
    - Timeline Communication Templates: How to negotiate unrealistic deadlines
    - Regression Testing Scope Clarity: When to test everything vs related features only
    - Fixed 3 contradictions: Staging deployment (no approval needed), Leave approval wording, Code review approval
    **→ Operations manual now handles all daily operational scenarios. No more "what do I do when..." confusion.**
  - v8.0: **FINAL ESSENTIALS - Simple Daily Clarity:** Added 6 simple sections (all checklists/tables for developer clarity):
    - Section 9B: Bug Priority System (P0/P1/P2/P3 severity levels with response times)
    - Section 21: Definition of Ready (when task is ready to start - prevents wasted work)
    - Section 21A: Code Review & QA Testing Checklists (exactly what to check)
    - Section 4B: Time Tracking & Billing Protocol (billable vs non-billable rules)
    - Section 4A: Requirement Clarification Questions (template questions to ask when task unclear)
    **→ Operations manual now COMPLETE for standard web agency. Simple, clear, no complexity.**
  - v7.0: **PHASE 1 - Self-Management Foundation:** Added 4 critical sections for autonomous operations:
    - Section 2A: Roles & Responsibilities Matrix (who does what, who reports to whom, RACI matrix)
    - Section 2B: Communication Channel Protocol (when to use Slack/Basecamp/Email/Phone)
    - Section 4A: Task Assignment & Pickup Protocol (how tasks get assigned, prioritized, picked up)
    - Section 9A: Decision Authority & Escalation Matrix (what decisions each role can make independently)
  - v6.0: Added detailed Monday/Friday Meeting structures with MOM templates (project-focused, not task-focused)
  - v5.0: Added comprehensive Attendance & Leave Management section with PM→HR approval workflow
  - v4.0: Added Team Member Onboarding, Updated Emergency Contacts (Slack/WhatsApp)
  - v3.0: Added 5 critical processes (Project Onboarding, Deployment, Scope Change, Emergency Response, Git Workflow)
  - v2.0: Added Definition of Done, Escalation, Response Times, Meeting Structures
  - v1.0: Initial manual (October 2025)

---

© 2025 WBCOM DESIGNS. All Rights Reserved.
