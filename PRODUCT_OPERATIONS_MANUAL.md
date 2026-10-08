# WBCOM DESIGNS - PRODUCT OPERATIONS MANUAL

This document covers how we build, test, release and support our own products: WordPress plugins, themes and their Pro add-ons. It sits beside the [Agency Operations Manual](WBCOM_Agency_Operations_Manual.md), which covers client projects.

**Why a separate manual:** a client project ships to one site that one client approves. A product update ships to thousands of live sites that nobody on our team can see. The cost of a mistake is far higher, so the rules are stricter.

Everything in the Agency manual about attendance, leave, communication etiquette, Slack and Basecamp usage still applies. This manual only adds what is different for product work.

---

## P1. Agency Work vs Product Work

| Topic | Agency (client project) | Product (plugin / theme) |
|-------|-------------------------|--------------------------|
| Who decides what to build | Client + PM | Product Owner, using customer data |
| Who approves "done" | Client | QA + Product Owner, against the release checklist |
| Where it runs | One site we can access | Thousands of sites with unknown themes, plugins, hosts and data sizes |
| How it ships | Deploy to client server | Tagged release, update pushed to every customer |
| Rollback | Restore our backup | Not possible. Customers update on their own. A bad release can only be fixed by a new release |
| Time tracking | Billable to client | Logged against the product, not billed |
| Bug source | Client and our QA | Customers via support, our QA, WordPress.org reviews and forums |

**Rule:** if you are unsure whether a task is agency or product work, ask the PM before starting. The checklists are different.

---

## P2. Product Roles

Every product has one named owner for each role below. The owners are listed in the product's Basecamp project description and in the repo `README.md`.

| Role | Responsibility | Typical person |
|------|----------------|----------------|
| **Product Owner** | Roadmap, priorities, Free vs Pro decisions, final call on "is this release ready" | PM or Management |
| **Lead Developer** | Architecture, code review approval, release branch, tagging | Lead / Senior Dev |
| **Feature Owner** | One developer per feature or plugin area: plan, build, tests, docs, QA fixes, release watch and bugs after release (Agency manual Section 2C) | Developers |
| **QA** | Pre-release smoke, card verification, regression | QA team |
| **Support Lead** | Ticket triage, turning tickets into cards, replying to customers when fixed | Support team |
| **Docs Owner** | Docs in the repo stay in step with the code | Developer who built the feature, reviewed by Docs Owner |

### Product RACI

| Activity | Product Owner | Lead Dev | Developer | QA | Support |
|----------|---------------|----------|-----------|----|---------|
| Roadmap and priorities | **A/R** | C | I | I | C |
| Free vs Pro placement | **A/R** | C | I | - | C |
| Feature / fix build (Feature Owner) | I | A | **R** | C | - |
| Code review | - | **A/R** | C | - | - |
| Pre-release QA | I | C | C | **A/R** | - |
| Release go / no-go | **A** | R | I | C | I |
| Changelog + release notes | A | **R** | C | C | I |
| Ticket triage | I | C | - | C | **A/R** |
| Customer reply after fix | I | - | - | - | **A/R** |

R = Responsible, A = Accountable, C = Consulted, I = Informed

---

## P3. Product Lifecycle

```
Idea / Ticket / Review
        ↓
Triage (Support Lead or Product Owner)
        ↓
Roadmap card (Product Owner prioritises)
        ↓
Build (Developer) → Code Review (Lead Dev) → Ready for Testing
        ↓
QA verify (per card) → Done
        ↓
Release branch → Pre-release smoke (QA) → Go / No-go (Product Owner)
        ↓
Tag + publish → Changelog → Support notified → Customers told
```

### Basecamp Card Table Columns (every product project)

| Column | Meaning | Who moves cards in |
|--------|---------|--------------------|
| **Triage** | New, not yet confirmed | Anyone |
| **Bugs** | Confirmed bug, reproduced | Support Lead / QA |
| **Roadmap** | Accepted feature, not yet scheduled | Product Owner |
| **Next Release** | Committed to the next version | Product Owner |
| **In Progress** | Being built | Developer |
| **Ready for Testing** | Built, reviewed, merged to the release branch | Developer |
| **Done** | QA verified | QA |
| **Released** | Shipped in a tagged version (card notes the version) | Lead Dev |
| **Won't Fix** | Closed with a written reason | Product Owner |

**Rule:** a card moves to Ready for Testing only after the code is merged and the developer has done the browser check in P6. A card QA bounces back gets a comment saying what was missed, and the missed check is added to the product's QA checklist (see P10).

---

## P4. Roadmap & Intake

### Where work comes from

| Source | Goes to | Who triages |
|--------|---------|-------------|
| Support ticket (Zoho Desk / Crisp) | Triage column | Support Lead |
| WordPress.org forum or review | Triage column | Support Lead |
| QA finding | Bugs column | QA |
| Team idea | Triage column | Product Owner |
| Client request touching a product | Triage column, tagged "client" (no client details, see below) | PM |

### Triage rules (within 2 working days)

For every card in Triage, the triager answers four questions in the card:

1. **Is it real?** Reproduced on a clean site with the latest version? Bug reports can be wrong, and an error can be intended behaviour.
2. **Reach:** how many customers hit it? (one site / one config / everyone)
3. **Impact:** data loss, payment, security, broken feature, or cosmetic?
4. **Where:** Free or Pro, and which surface (frontend, admin, REST API, email)?

Then the card goes to **Bugs**, **Roadmap** or **Won't Fix** (with reason).

### Free vs Pro placement

The Product Owner decides. Default guide:

- **Free:** core functionality a site needs to be usable, security fixes, compatibility, accessibility.
- **Pro:** advanced workflows, integrations, automation, extra layouts, things a growing site pays for.
- **Never:** move an existing Free feature into Pro. Customers already rely on it.

### Client requests that touch a product

If a client asks for a change to one of our products, the PM decides with the Product Owner whether it becomes:
- a **product feature** (everyone gets it, logged as product time), or
- a **client customisation** (built as a separate add-on or via hooks, billed to the client).

Never add client-specific code or settings to a product.

The discussion with the client stays in the client's own Basecamp project (client isolation, Agency manual Section 2B). The product card describes the general need only, with no client name, data or screenshots, and links back to the client card for the internal team.

---

## P5. Building Product Features

Before writing code, the developer checks these. Each one exists because skipping it caused real bugs before.

### A. Reuse before you write

- If the repo has `audit/manifest.json` (or a free/pro manifest pair), read it first. It lists every function, hook and REST route. Reuse what exists instead of adding a near-duplicate.
- Read the repo's `CLAUDE.md` / architecture docs for conventions.
- When you add a hook, endpoint or option, update the manifest in the same PR.

### B. Three entry points for every feature

Every feature that stores data must be reachable from all three:

1. **Frontend:** members / visitors can use it.
2. **Admin:** the site owner can see and manage it.
3. **REST API:** it can be read and written through the API.

A table or setting that only one of these can reach is a half-finished feature. If one entry point is deliberately left out, say so in the PR and the manifest.

### C. Large-site readiness (baseline, not a follow-up)

Customer sites are big. Every list, grid, table or query must work with **2,000+ rows** on day one:

- [ ] **Pagination:** `LIMIT`/`OFFSET` + `COUNT(*)` + prev/next in the UI. No unbounded queries.
- [ ] **Indexes:** every `WHERE` / `ORDER BY` / `JOIN` column is indexed.
- [ ] **No N+1:** no queries inside a `foreach`. Batch-fetch first.
- [ ] **Counts via `COUNT(*)`:** never `count()` a full result set just to show a number.
- [ ] **Filter + sort:** at least the main filter (status / type) and sort (newest / oldest).
- [ ] **Caching:** shared data has a cache key and is cleared on write.
- [ ] **Concurrency:** the UI handles "already deleted / already taken" without errors.

Test it: seed 1,000+ posts / 500+ users with WP-CLI and check the page still loads quickly.

### D. UI rules

- [ ] Works at **390px** mobile width, with a mobile breakpoint in the same PR.
- [ ] Works in **dark mode** (use design tokens, never raw hex colours).
- [ ] Works in **RTL** (`margin-inline-*`, not `margin-left/right`).
- [ ] **Accessible:** semantic HTML, labels on icon-only buttons, keyboard reachable.
- [ ] Handles **empty, loading and error** states.
- [ ] Looks right under our own themes and at least one popular third-party theme.

### E. Never break existing sites

- [ ] Database changes run through a versioned upgrade routine. No data is dropped.
- [ ] Renamed options, hooks or meta keys keep the old name working (read old, write new) for at least two releases.
- [ ] Removed hooks or functions are deprecated first (`_deprecated_function()`), not deleted.
- [ ] Free and Pro: Pro checks the Free version it needs and shows a clear notice if Free is too old.

---

## P6. Product Definition of Done

### Developer (before Ready for Testing)

- [ ] Code reviewed and approved in a GitHub pull request
- [ ] CI is green: PHPCS (WPCS), PHPStan, PHPUnit, Plugin Check
- [ ] Large-site checklist (P5-C) done for every list / query touched
- [ ] Browser-checked as each affected role (admin, member, guest) at desktop and 390px
- [ ] Screenshots attached to the card, each labelled with **viewport + role**
- [ ] All three entry points work (P5-B)
- [ ] Manifest updated if a hook / endpoint / option was added
- [ ] Docs updated in `docs/website/` if behaviour changed
- [ ] Changelog line added to the PR description (P8 format)

### QA (before Done)

- [ ] Reproduced the original bug on the old version, confirmed fixed on the new one
- [ ] Checked the surrounding feature, not just the exact steps on the card
- [ ] Checked as the site owner would see it: settings, defaults, emails, templates
- [ ] No new PHP notices or JS console errors

**QA findings are input, not verdicts.** Broken functions are fixed without debate. For layout / UX preferences ("feels empty", "should be wider"), the developer reproduces at the exact viewport, judges it as the site owner and end customer would, and pushes back with a reason if the current behaviour is correct. If it is genuinely subjective, add a filter so site owners can change it.

---

## P7. Release Process

### Release cadence

| Type | When | Contains |
|------|------|----------|
| **Patch** (1.4.**2**) | As needed, usually every 2 weeks | Bug fixes only |
| **Minor** (1.**5**.0) | Planned, about every 1-2 months | New features + fixes |
| **Major** (**2**.0.0) | Rare, announced ahead | Breaking changes, big redesigns |
| **Security** | Same day if possible | Security fix only, nothing else |

### Release branch

1. Lead Dev creates `release/X.Y.Z` from `develop` when the Next Release column is done.
2. Only fixes for problems found during the release QA go into the release branch after that.
3. After release, merge back to `main` and `develop`, then tag `X.Y.Z`.

### Pre-release checklist (QA owns, Product Owner signs off)

- [ ] Every card in Next Release is in Done
- [ ] Full smoke run of the product's core paths, per role, at desktop and 390px
- [ ] Contract check: every saved setting is actually read and applied; every hook fired is consumed
- [ ] Upgrade test: install the **previous** released version with data, then update. Nothing lost, no errors
- [ ] Fresh install test on a clean site
- [ ] Tested on the minimum and latest supported WordPress and PHP versions
- [ ] Tested with the latest WooCommerce / BuddyPress (where the product depends on them)
- [ ] Free + Pro: tested together at the new versions **and** new Pro with the oldest Free it supports
- [ ] Plugin Check passes (required for WordPress.org products)
- [ ] Version number bumped everywhere (plugin header, constants, `readme.txt` stable tag, `package.json`)
- [ ] `readme.txt` changelog written (P8)
- [ ] Docs updated
- [ ] Build zip installs and activates on a clean site

### Go / No-go

The Product Owner gives a written "Go" in the Basecamp release card. **No Go, no tag.**

**Do not release:**
- on Friday after 3 PM or before a public holiday
- with a known P0 / P1 bug open against this version
- without the upgrade test

### After release (same day)

- [ ] GitHub release published (P8 format)
- [ ] Cards moved to Released with the version number
- [ ] Support team told what changed and which tickets it fixes
- [ ] Each Feature Owner watches support and errors for their feature
- [ ] Support replies to every customer whose ticket was fixed
- [ ] Watch support and forums for 48 hours. Two or more reports of the same new problem → hotfix

### Hotfix

A new release that breaks sites is a **P0**:
1. Post in `#emergencies` with the version and symptom.
2. Fix on `hotfix/X.Y.Z+1` from the tag, with only the fix in it.
3. Shortened QA: the broken path, the upgrade test, a fresh install.
4. Release, then write a short post-mortem in Basecamp within 2 working days (what broke, why QA missed it, which check was added).

---

## P8. Changelog & Release Notes

Same format in `readme.txt` and the GitHub release body. Used by WooCommerce, EDD, ACF and most major plugins.

```
= 1.4.2 - May 2026 =

One-line summary. Skip if the bullets speak for themselves.

* New      - Description.
* Improve  - Description.
* Fix      - Description.
* Security - Description.
* Dev      - Description.
* Compat   - Aligned with Plugin X.Y.Z. Install both updates together.
```

**Rules:**
1. One action prefix per bullet: `New`, `Improve`, `Fix`, `Security`, `Dev`, `Compat`, padded so the dashes line up.
2. Order: New, Improve, Fix, Security, Dev, Compat.
3. One sentence per bullet. A second sentence only for a hard detail (filter name, setting, threshold).
4. Written for the site owner, not for us. No ticket IDs, branch names or commit hashes.
5. No marketing intros, no feature-themed subheadings, no emoji, no em-dashes.
6. Release title: `Plugin X.Y.Z - one-line summary`.
7. Free and Pro released together link to each other's release.

---

## P9. Support to Bug Loop

```
Customer ticket
    ↓
Support Lead reproduces (latest version, clean site + customer's setup if needed)
    ↓
Not a bug → answer customer, add to docs/FAQ if asked twice
Bug → Basecamp card in Bugs (link ticket, steps, version, environment)
    ↓
Customer told: "Confirmed, we'll update you when it's fixed" (no dates promised)
    ↓
Fixed + released → Support replies with the version number
```

### Bug card must include

- Product + version, Free or Pro
- WordPress, PHP, theme and active plugins (from Site Health info)
- Exact steps to reproduce on our site
- Expected vs actual result
- Link to the support ticket(s)
- Reach (one site / some / everyone) and severity (Agency manual Section 9B)

### Response targets

| Severity | First reply to customer | Fix shipped |
|----------|-------------------------|-------------|
| P0 - site broken / data loss / security | 4 hours | Hotfix, same or next day |
| P1 - major feature broken, no workaround | 1 working day | Next patch release |
| P2 - broken with a workaround | 1 working day | Next minor release |
| P3 - cosmetic / enhancement | 2 working days | Roadmap |

### Aging

Every Monday the Support Lead lists bugs older than 30 days in the planning meeting. Each one gets a release target or moves to Won't Fix with a reply to the customer.

---

## P10. Learning Loop

The goal is that the same kind of bug does not ship twice.

- **Every QA bounce** adds one line to the product's QA checklist describing the check that would have caught it.
- **Every customer-found bug** gets a one-line "why we missed it" note on the card before it moves to Released.
- **Monthly product retro (30 min per product, Product Owner leads):**
  1. Which bugs did customers find that we didn't?
  2. Which checks were added this month?
  3. Which hotfixes did we need, and why?
  4. One process change to try next month.

---

## P11. Product Metrics

Measure results, not activity. The Product Owner reviews these monthly.

| Metric | What it tells us | Target |
|--------|------------------|--------|
| **Escaped bugs** | Bugs customers reported against the latest release | Trending down |
| **Hotfixes per release** | How often a release had to be patched within 7 days | ≤ 1 in 5 releases |
| **Card reopen rate** | Cards bounced from QA back to dev | ≤ 15% |
| **Cycle time** | Days from In Progress to Released | Trending down |
| **Bug age** | Median age of open bugs | ≤ 30 days |
| **Support reply time** | First reply to customers | Meets P9 targets |
| **WordPress.org rating** | Customer sentiment (free products) | ≥ 4.5 |

Per-developer ownership measures (escaped bugs in owned work, reopen rate, risks raised early) are in Agency manual Section 2C-E. Track the table above per product, not per person. They show where the process is weak. They are not individual performance scores.

---

## P12. Documentation

- All product docs live in the product's GitHub repo under `docs/website/`, written in Markdown and committed with the code.
- Images go in `docs/website/images/` next to the Markdown.
- The developer who changes behaviour updates the docs in the same PR. The Docs Owner reviews.
- Folder shape (same for every product):

```
docs/website/
├── docs_config.json
├── images/
├── getting-started/
├── settings/
└── developer-guide/
```

---

## P13. AI-Assisted Development

AI coding tools (Claude Code and similar) are allowed for product work, with these rules:

- **Same bar as human code.** AI-written code goes through the same PR review, CI and Definition of Done. "The AI wrote it" is never a reason to skip a check.
- **You own it.** You must understand and be able to explain every line you submit.
- **No secrets or customer data in prompts.** No credentials, licence keys, customer emails or exported customer databases.
- **No AI attribution in commits or PRs.** No `Co-Authored-By` AI lines or "Generated with" footers.
- **Verify claims.** If an AI says something is fixed or tested, check it in the browser yourself before moving the card.

---

## P14. Quick Reference

| Question | Section |
|----------|---------|
| Is this agency or product work? | P1 |
| Who owns this product? | P2 |
| Which Basecamp column? | P3 |
| Should this be Free or Pro? | P4 |
| A client wants a product change | P4 |
| What must I check before writing code? | P5 |
| When is my product card done? | P6 |
| How do we release? | P7 |
| How do I write the changelog? | P8 |
| A customer reported a bug | P9 |
| A release broke sites | P7 - Hotfix |
| Can I use AI tools? | P13 |

---

## Document Control

- **Owner:** Product Owners + Lead Developers
- **Version:** 1.0
- **Last Updated:** October 2026
- **Next Review:** January 2027

© 2026 WBCOM DESIGNS. All Rights Reserved.
