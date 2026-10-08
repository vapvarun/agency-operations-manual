# Wbcom Designs - Operations Manuals

How the Wbcom team works on client projects and on our own products (themes and plugins).

## The four documents

| Document | Read it for | Who reads it |
|----------|-------------|--------------|
| [Quick Reference Card](QUICK_REFERENCE_CARD.md) | One-page summary of daily rules. **Start here.** | Everyone |
| [Agency Operations Manual](WBCOM_Agency_Operations_Manual.md) | Roles, communication, ownership, attendance and HR, client project process, meetings, escalation | Everyone |
| [Product Operations Manual](PRODUCT_OPERATIONS_MANUAL.md) | Product policy: roadmap, Free vs Pro, release policy, support targets, product metrics | Product team, PMs, Leads |
| [Developer Playbook](DEVELOPER_PLAYBOOK.md) | Step-by-step how-to: bug fixing, debugging, build rules, self-checks, quality gates, QA, release steps | Developers, QA, Leads |

**New team member:** Quick Reference Card → the 9 "start here" sections it lists → Developer Playbook (developers / QA) or Product Operations Manual (product team).

## Which document owns which topic

Each topic is written in **one** place. Other documents only link to it. If two documents ever disagree, the owner below wins, and the other one gets fixed.

| Topic | Owner |
|-------|-------|
| Roles, reporting lines, RACI, who approves what (including code review approvers) | Agency 2A, 21A |
| Communication channels, response times, client isolation, Scope of Work | Agency 2B |
| Feature Owner model, daily update, weekly 1:1, 50% checkpoint, ownership measures | Agency 2C |
| Social media sharing (blogs, videos, releases) | Agency 2D |
| Attendance, leave, HR, KPIs, evaluations | Agency 3, 14 |
| Task priority (High / Medium / Low), task assignment | Agency 4, 4A |
| Meetings, standup, MOM, QA Review, Product Review | Agency 8 |
| Decision authority, escalation timeline | Agency 9A, 22 |
| Client-project bug timings by severity | Agency 9B (Quick Reference table) |
| Client deployment approval and timing, git branches, commit format | Agency 16, 19 |
| Emergencies | Agency 18 (follows the 2B contact chain) |
| Credentials (one "Project Credentials" document) | Agency 13A |
| Who signs off "done" (developer / QA / PM) | Agency 21 (+ Product P6 for products) |
| Product roles, intake, Free vs Pro placement | Product P2-P4 |
| Product reply and fix targets, paying-customer rule | Product P9 |
| Release cadence, Go / No-go, release timing, hotfix trigger, Free / Pro lockstep | Product P7 |
| Deprecation and rename periods | Product P5-E |
| Changelog format | Product P8 |
| Product metrics | Product P11 |
| AI-assisted development | Product P13 (+ client-data rule in Agency 9) |
| Bug severity grid (P0-P3 thresholds) | Playbook D3 |
| Bug brief, verdict and code review comment formats | Playbook D4-F, D9-F, D11 |
| Build rules, UI rules, test viewports | Playbook D5, D6 |
| Self-checks, quality gates, PR / CI | Playbook D7, D8 |
| QA method, role ladder, test accounts | Playbook D9 |
| Release QA tiers and release steps | Playbook D10 |
| Standard Basecamp card table and card-writing rules | Playbook D11 (client columns: Agency 4A) |
| Docs format and folder shape | Playbook D13 (docs location: Product P12) |
| Quick Reference Card | Summarises only, never adds a rule |

## Changing these documents

- **No real names in this repo.** It is public and the team changes over time. Never write a real client name, client site, or team member's name. Use roles (PM, Lead Dev, Feature Owner, Support Lead) and placeholders (`[Name]`, `[client]`, `[product]`). Made-up example names ("John is fixing the header bug", `clientxyz`) are fine. Who holds each role lives in Basecamp and Slack, not here.

- Change the rule in its **owner** document, then update any summary that repeats it (usually the Quick Reference Card).
- Make changes through a pull request, never directly on `main`.
- Each document has a Document Control section with its version and next review date.
