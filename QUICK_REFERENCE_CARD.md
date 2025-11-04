# WBCOM DESIGNS - QUICK REFERENCE CARD
**Print this and keep at your desk**

---

## ✅ THE 3 RULES

### Rule 1: What "Done" Means

**Developer:**
□ WPCS passes (0 errors)
□ Tested + screenshot attached
□ Time logged

**QA:**
□ No critical bugs
□ Screenshots attached

**PM:**
□ Client approved

---

### Rule 2: When Stuck

**If blocked >30 min:**
→ Post in Slack: "Stuck on [X], tried [Y], need help with [Z]"

**Who to ask:**
- Technical → @Lead-Dev
- Task unclear → @PM
- Client question → @PM (never client directly)

---

### Rule 3: Response Times

| What | When |
|------|------|
| Client question | Same day (4 hrs) |
| Help request | Same day (2 hrs) |
| Code review | 24 hours |
| QA testing | 24 hours |
| Urgent/Security | Immediately |

---

## 📅 DAILY ROUTINE

### For Developers:

**Morning (10:00 AM)**
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

---

### For PM:

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

## 🕐 MEETING TIMES

| Meeting | When | Duration |
|---------|------|----------|
| **Daily Standup** | 10:15 AM | 15 min |
| **Weekly Review** | Fri 6:00 PM | 50 min |
| **Client Meetings** | 3-6 PM | As needed |

---

## 🛠️ TOOLS

| Tool | Purpose |
|------|---------|
| **Basecamp** | Tasks, client communication |
| **Slack** | Daily updates, team chat |
| **Time Tracker** | Log hours |
| **WPCS** | Code quality (run before commit) |
| **Plugin Checker** | Plugin standards |

---

## 📞 WHO TO CONTACT

| Issue | Contact |
|-------|---------|
| Stuck on code | @Lead-Dev |
| Task unclear | @PM |
| Client question | @PM |
| Urgent/Security | @PM + @Lead-Dev |
| Absent/Leave | Post in #attendance |

---

## 🚨 ESCALATION

```
Stuck on task (30 min)
    ↓
Ask in Slack
    ↓
Still stuck (2 hrs)
    ↓
PM adjusts timeline
```

```
Client complaint
    ↓
Tell PM immediately
    ↓
PM responds (4 hrs)
```

---

## 💡 QUICK TIPS

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

## 🔄 KEY PROCESSES

**New Project?** → Section 14 (Project Onboarding Checklist)
**Ready to Deploy?** → Section 15 (Deployment Process - needs PM approval)
**Client Wants Changes?** → Section 16 (Scope Change - don't commit immediately)
**Site Down?** → Section 17 (Emergency Response - post in #emergencies)
**Git Branching?** → Section 18 (Use feature/*, bugfix/*, hotfix/*)
**New Team Member?** → Section 19 (Onboarding - mentor assigned, first day/week/month)

---

## ⚠️ RED FLAGS

**Report to PM immediately (Slack/WhatsApp):**
- Security issue
- Site down (post in #emergencies + follow Section 17)
- Client escalation
- Stuck >2 hours on urgent task
- Missing credentials to start work

**After hours:** Message PM on Slack/WhatsApp, if no response in 15 min → Message Lead Dev

---

## 📊 SUCCESS METRICS

**Target:**
- QA Pass Rate: 85%+
- Deadlines Met: 95%+
- Client Response: <4 hours
- Code Reviews: <24 hours

---

**Questions? Ask PM or check full manual in Basecamp.**

© 2025 WBCOM DESIGNS
