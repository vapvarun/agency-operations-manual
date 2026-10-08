# WBCOM DESIGNS - DEVELOPER PLAYBOOK

**The step-by-step "how" for every developer and QA engineer.** The [Agency Operations Manual](WBCOM_Agency_Operations_Manual.md) and the [Product Operations Manual](PRODUCT_OPERATIONS_MANUAL.md) say *what* we expect and *who* decides. This playbook says *how to do the work*.

**The steps are the same for every plugin, theme and client project.** Where a client project differs, the step says **Client project:**. Where it only applies to our own products, it says **Product:**.

**Build your own tools from it.** Every step is written so you can follow it by hand with ordinary tools (browser, WP-CLI, git, PHPCS, PHPStan, grep, Basecamp). Turning a step into a script, a checklist, an editor snippet or any helper you like is encouraged. The steps stay the same. Only how fast you do them changes.

---

## Contents

- D1. The QA Cycle at a Glance
- D2. Before You Touch Code
- D3. Fixing a Bug
- D4. Debugging Method
- D5. Building a Feature: Build Rules
- D6. UI Rules
- D7. Self-Checks Before Review
- D8. Quality Gates: Commit, Push, Card, Release
- D9. QA of a Card
- D10. Release QA & Release Steps
- D11. Basecamp Conventions & Evidence
- D12. Replying to Customers & Clients
- D13. Documentation
- D14. Repo Setup Checklist
- D15. What Does NOT Count as Tested

---

## D1. The QA Cycle at a Glance

Every change goes through the same cycle. Know where your card is and what the next person needs from you.

```
Intake (ticket / client / QA)
   ↓  Triage: real? reach? impact? where?            (D3 steps 1-5)
Bugs / Scope
   ↓  Root cause + reach, card filled                (D3 steps 6-7, D4)
Ready for Development
   ↓  Owner builds + self-checks + regression guard  (D5, D6, D7)
   ↓  Pre-commit gate → PR → CI green → code review  (D8)
Ready for Testing   (only after your own browser check)
   ↓  QA verifies on the role ladder                 (D9)
Done (products)  |  Ready for Deployment → PM approval → Deployed → Done (client projects)
   (or back to Bugs with a reason)
   ↓  Release QA + release (products, D10)
Released / Deployed → 48 h watch → customer/client told  (D12)
   ↓  Anything missed → new check added              (learning loop)
```

**Your part as the Feature Owner (Agency manual Section 2C):** you are responsible from Ready for Development until the change has been live for 48 hours without problems. QA checks your work. QA is not where your testing starts.

---

## D2. Before You Touch Code

### A. Read in this order

1. The **project guide** at the repo root (the READ-FIRST file): conventions, architecture, where files go, how to run the gates.
2. **`audit/manifest.json`** (or `manifest.summary.json`) if the repo has one: every REST route, table, option, hook, capability, block, cron job and CLI command.
3. **`CAPABILITIES.md`**: what the product can do, at buyer level, with file:line.
4. `audit/ROLE_MATRIX.md`, `audit/CODE_FLOWS.md`, `docs/qa/` if present.
5. **Client project:** the Scope of Work, all client messages on the card, and the project channel history.

**If two sources disagree:** manifest → CAPABILITIES → code. Dated notes and old plans are history only. **Check every doc claim against the code before you plan.** Features marked "coming soon" have often already shipped, and teams have planned duplicate builds because of it.

Folder meaning: `audit/` = generated inventory (don't hand-edit), `plan/` = human plans, `docs/` = customer-facing docs.

### B. No inventory? Build one with grep

Exclude `vendor/`, `node_modules/` and minified files. List **everything**, not "the important ones":

```bash
grep -rn "register_rest_route" --include=*.php .
grep -roh "['\"]wp_ajax_[a-zA-Z0-9_]*" --include=*.php . | sort -u
grep -roh "do_action\s*(\s*['\"][^'\"]*" --include=*.php . | sort -u
grep -roh "apply_filters\s*(\s*['\"][^'\"]*" --include=*.php . | sort -u
grep -rn "register_setting\|get_option\|update_option" --include=*.php .
grep -rn "register_post_type\|register_taxonomy\|add_shortcode\|add_menu_page\|add_submenu_page" --include=*.php .
grep -rn "wp_schedule_event\|wp_schedule_single_event\|as_schedule\|WP_CLI::add_command" --include=*.php .
grep -roh "current_user_can\s*(\s*['\"][^'\"]*" --include=*.php . | sort -u
```

### C. Reuse first

Search for an existing helper, getter, renderer, hook or setting before adding one. If the same behaviour exists in several places, the fix is to **consolidate it into one owner** (one getter, one renderer, one CSS class set), not to patch each copy.

### D. Map every surface the change touches

A behaviour lives in more places than the card names. Before changing it, list every file that implements it (file:line) across:

- **Free and Pro** (and any paired add-on)
- **All three entry points:** frontend, admin, REST API
- Blocks, shortcodes, widgets, emails, cron, CLI, import/export

Keep this list in the card (or in `docs/qa/SURFACES.md` if the repo has one). Before handing to QA, mark each surface: **fixed**, **checked - unaffected**, or **not covered (reason)**.

### E. Plan before building (features)

Write a short plan in the card. For new features, mark each of these **already good / needs work / out of scope**:

1. REST contract
2. Database indexes for large data (100k rows)
3. Caching
4. Free/Pro coupling
5. Release packaging (build script, Plugin Check on the built zip)
6. Activation experience (sensible defaults, pages created once)
7. Feature-toggle defaults (heavy or niche features OFF)
8. Acceptance tests written before code

Get the Reviewer's OK on the approach before building (Agency manual 2C).

---

## D3. Fixing a Bug

### Step 1: Read the whole report

- Read the full thread and open every attachment. Don't work from the subject line.
- Number every separate point the reporter raised, in their own words. Each one gets answered.
- Sort it: **real issue** / already being handled / automated noise / spam / sales or billing only. Billing and licence questions go to the billing person.
- When unsure whether it's real, file it. Closing a non-bug is cheaper than missing a regression.

### Step 2: Look for an existing card

Search the board across **every** column, including cards already in testing. If one exists, comment on it instead of creating a duplicate:

- Same reporter again: `[Reminder #N] Same customer (...) reported this again. Please update on progress.`
- New reporter: `[Priority Escalation] New customer (...) reported the same issue. Now affecting N customers.`

**3 or more reporters = systemic. Escalate.** After a release, 2 reports of the same new problem = hotfix (Product manual P7).

### Step 3: Triage on reach, impact and location

- **Reach:** universal (clean install, default settings, default theme) or site-specific
- **Impact:** road-block (no workaround), degraded, or cosmetic
- **Location:** core path or edge case

| | Core path | Edge case |
|---|---|---|
| Universal, road-block | **P0** | **P1** |
| Universal, degraded | **P1** | **P2** |
| Site-specific, road-block | **P1** | **P2** |
| Site-specific, degraded | **P2** | **P3** |
| Cosmetic | **P2** | **P3** |

Response and fix times for each level: client projects, Agency manual Section 9B; products, Product manual P9. Who has the final say on the level: the PM (client projects) or the Product Owner (products).

- **Product:** paying-customer and free-user priority rules are in Product manual P9.
- "Site-specific" is a finding, not a dismissal.
- Category (helps routing): Fatal, Data, Display, Logic, Permission, Performance, Integration, JavaScript, AJAX/Hooks, Silent Failure, Security.

### Step 4: Reproduce before anything else

- Use a **clean test site running the released code** (the latest tag, not your dev branch). Check the installed version first.
- Reproduce **as the reporter's role**, through the real UI. Watch the browser console and network tab.
- Something you can only trigger through WP-CLI is not a bug until it reproduces in the UI.
- Before asking the reporter anything, answer it yourself from git history, code, order data or logs. To check for a regression: `git show <tag>:<file>` across recent tags.
- **Can't reproduce?** That's a finding, not a card. Write down exactly what you tried and ask for the specific missing detail.

**Rule: no card and no reply until you have seen it fail in a browser yourself.**

### Step 5: Scope gate

Not a bug card if it is: by design, a server / host / config problem, a third-party conflict outside our code, or a custom-development request. These get a helpful reply (and a feature note if relevant). Exception: our plugin screen broken by theme CSS **is** our bug. The plugin owns its look.

### Step 6: Root cause and reach

- Name the file:line, **how you established it** (reproduced in browser as role X / WP-CLI / code reading only) and your confidence.
- Search **every caller** of the function, option, hook or route. Wrapper methods hide callers: searching `Foo::bar` misses `$obj->bar()`.
- Search for **literal values** too. The same rule is often copied 2-5 times.
- Check Free + Pro, all entry points (D2-D), every role that can reach it.
- Check object states (empty, one item, 21+ paged, trashed, gated) and boundaries (null, unset vs false, first and second run, 5,000 rows).

### Step 7: File the card

- Title: `[SUPPORT] <one concrete symptom>` for customer reports, or `<area>: <symptom>` otherwise.
- Column: **Bugs**, or **Possible Bug** if not yet reproduced. When it is confirmed, root-caused, has a fix direction and an owner → **Ready for Development**. **Product:** who may move a card into each column is in Product manual P3.
- The card body uses the **bug brief** (D4-F). Customer reports also include the customer's words verbatim with source and date, whether they are a paying customer, and 2-4 exact questions still needed from them ("ASK" for unknowns).
- Add a private note on the support ticket: `Internal: <product> - <issue> - card <url> - <one-line answer for the agent>`. A card without this note is incomplete.
- Assign to the product family's named owner (listed in the product README). Otherwise leave it unassigned for the lead to pick. Never guess an assignee.

### Step 8: Fix

**Fix it yourself** when the cause is clear, the change touches 1-3 files you understand, there's no schema change, and you can test it locally.

**Escalate to your Lead** when it spans several plugins or core, 3+ systems or a race condition, needs a database change, needs production or server access, or you're stuck after 2 investigation attempts.

**After 3 failed fix attempts, stop.** It's probably an architecture problem. Discuss it with the Lead before trying again.

- Fix the **root cause, once, where all callers route through**. Not only in the path the ticket names.
- Never "fix" a correct guard and never weaken a test to make a card go away. An invalid card is a fine outcome: close it with proof.
- **The regression guard ships in the same commit:** a test, or a new step in the QA checklist / journey that would have caught this bug.

### Step 9: Hand to QA

Run the gates (D8), do your own browser check (D7-G), then move the card to **Ready for Testing** with a comment: commits, retest steps, surfaces covered, roles and viewports checked, and what you did **not** cover.

### Step 10: After it ships

- **Done ≠ released.** Before telling anyone it's fixed, confirm the fix is in a released version (or deployed, for client projects).
- Customer reply rules: D12.

---

## D4. Debugging Method

### A. Set up

`WP_DEBUG`, `WP_DEBUG_LOG` and `SCRIPT_DEBUG` on. Watch `wp-content/debug.log`, the browser console and the network tab. Note the debug.log size before you start, so you can see what's new.

### B. Reproduce and record

Use the reporter's role, configuration and theme, through the real UI. Screenshot the failure **before** changing anything.

### C. Isolate

1. **Conflict test by halving:** deactivate all plugins, then re-activate half at a time until one remains (50 plugins ≈ 6 rounds).
2. **On a live site:** never deactivate plugins for everyone. Use Site Health → Troubleshooting mode (affects only your session) or a staging copy.
3. **Theme switch:** try a default Twenty-series theme.
4. **Found the conflict?** Check hook priorities, filter return types, global or class name collisions, duplicate JS libraries and REST route collisions. Fix it if the conflict is in our code. Tell both vendors if it's between third parties.

### D. "Nothing happens" (silent failures)

Check in this order: AJAX handler not registered (returns `0`), nonce failing, capability check false, hook removed or wrong priority, filter returning the wrong type, an error swallowed somewhere. Log at each decision point.

REST status codes: **404** = route not registered or permalinks need flushing. **401/403** = auth or permission. **500** = PHP error (check debug.log). Empty response = often missing `show_in_rest`.

### E. Confirm the cause

- The cause you state must be the actual cause, not a symptom that disappeared for a reason you can't explain.
- Performance claims ("batched", "no N+1") are **measured** (Query Monitor or a query count), not asserted. Index claims need `EXPLAIN`.
- A scanner's severity label is not evidence. Check it by hand.

### F. Bug brief template (paste into the card)

```
BUG: <title>   Severity: P0-P3   Product/Project: <name> v<x>   Category: <...>
REPRODUCTION: numbered steps / Expected / Actual / How often
ENVIRONMENT: WP, PHP, theme, plugin versions, other active plugins, browser/device, URL
EVIDENCE: commands, URLs, screenshots, log lines, DB before/after
ROOT CAUSE: file:line @commit / established by (browser as role X, CLI, code reading) / confidence + why
REACH: callers and copies found (or "searched, none") / Free-Pro / entry points / roles
NOT VERIFIED: <never empty by default>
TRIED: action -> result
FIX: file:line / change / test that proves it
VISUAL PROOF: before / after
```

Whoever picks up a brief first re-checks the load-bearing claims: does the repro still hold, is the cited code really the cause, is the reach complete? If any fails, send the brief back. Don't build on it.

---

## D5. Building a Feature: Build Rules

These apply to new code. **In older plugins, follow the existing structure. Don't half-migrate a file to a new pattern.**

### A. Architecture (new plugins and new modules)

Seven layers. Each layer may only depend on layers with a lower number:

1. **Bootstrap:** main file, `Core/Plugin.php`
2. **Container:** lazy factories only
3. **Repository:** `Repository/<Domain>Repository.php`. All custom-table SQL lives here
4. **Services:** `Services/<Capability>Service.php`. Business logic. Returns data, never echoes HTML, never calls `wp_die()`
5. **Surface adapters:** REST controllers, CLI, blocks, shortcodes. Thin: validate, call a service, format. A REST handler is about 30 lines max
6. **Templates:** `templates/`, presentation only, no SQL, theme-overridable
7. **Admin:** one class per page, saves through REST (or `admin_post_*`)

- New tables: a numbered migration with `ENGINE=InnoDB DEFAULT CHARSET=utf8mb4`. Migrations must be safe to run twice.
- One-off seed or cleanup scripts are service methods, never loose PHP files in the plugin root.
- A block, shortcode and widget that show the same thing share **one renderer and one option schema**. Need two more options? Add them to the schema. Don't create a second block.

### B. Security

- **Capability check first, then nonce.** A nonce stops CSRF; it is **not** permission. Never use `is_admin()` as a permission check.
- Sanitize input, always after `wp_unslash()`: `sanitize_text_field( wp_unslash( $_POST['x'] ) )`, `absint( $_GET['id'] )`. Read explicit keys only. Never loop over `$_POST`.
- Escape late on output: `esc_html`, `esc_attr`, `esc_url`, `wp_kses_post`, `esc_html__`.
- `$wpdb->prepare()` for every query with a variable, `$wpdb->esc_like()` for LIKE.
- `wp_safe_redirect()` + `exit`. ABSPATH guard at the top of every PHP file.
- Every REST route has a `permission_callback`. Auth failure returns `WP_Error( ..., [ 'status' => 401 ] )`, never `false`.
- Rate-limit public (`nopriv`) endpoints. Validate URLs you fetch. Validate upload MIME types. Never use a user-supplied path.

### C. REST & data

- Namespace `{prefix}/v1`. **Product:** the frontend is 100% REST. No new `admin-ajax` (at most two legacy exceptions per plugin, e.g. a notice dismiss).
- List responses: `{ "items": [...], "total", "pages", "has_more" }`. `has_more = (offset + count) < total`, never `count === per_page`.
- Cap `per_page` in the handler: `min( absint( $per_page ), 100 )`. Add `ID DESC` as a tiebreaker to every non-unique sort.
- Single items include `id`, `created_at`, `updated_at` (ISO 8601 UTC). Validation errors go in `data.errors`, keyed by field.
- Every write fires `before_` and `after_` actions with all data as parameters. Listeners never read `$_POST`.
- Document every endpoint (`docs/REST-API.md` or the OpenAPI file).

### D. Settings

- `register_setting()` always has a `sanitize_callback`. Unchecked checkboxes save `false`.
- **One getter per setting.** Everyone calls it. Never re-derive the default inline with `??`.
- Feature toggles live in one central array read through one helper. Common features default ON; heavy or niche features default OFF.
- No number input with a raw `-1` default for "unlimited". Use an "Unlimited" checkbox.

### E. Performance (works at 2,000+ rows on day one)

- No `posts_per_page => -1`, no `query_posts`, no `session_start`, no option writes on the frontend, no external HTTP in the page request (move it to a background job).
- **Pagination:** `LIMIT` + `COUNT(*)` + prev/next. Use cursor pagination (`WHERE id < $cursor`) on tables over 100k rows.
- **Indexes:** every `WHERE` / `ORDER BY` / `JOIN` column. Check with `EXPLAIN`. If `key` is NULL, add an index.
- **No N+1:** prime caches before loops (`update_meta_cache`, `update_object_term_cache`). Never query inside a `foreach`.
- **Counts:** `SELECT COUNT(*)`, never `count()` of a full list.
- **Caching:** `wp_cache_*` with a `last_changed` key per group, cleared on write. Transients for cross-request data. No custom cache classes. Never delete transients with `LIKE`.
- Enqueue assets only where they are used. Admin assets only on our own screens. Scripts use `'strategy' => 'defer'`.
- Budgets (gzipped): public CSS ≤ 35 KB, public JS ≤ 40 KB, block `view.js` ≤ 20 KB. A block render ≤ 10 queries.

### F. Background jobs (use the lightest option that works)

1. Compute on demand + cache (no job at all)
2. A one-off job when something happens
3. A one-off job scheduled for a known time, re-armed after it runs
4. A recurring job that arms itself on write and stops when the queue is empty
5. A recurring job at the lowest cadence that works (daily or weekly)

- **Never** a job that runs every few minutes while there is nothing to do.
- Check if the job is already scheduled before scheduling. Handlers are idempotent and process in batches.
- Schedule on `init` / `wp_loaded`, **never on `plugins_loaded`** (it silently does nothing there). Confirm it was actually scheduled.
- Clear all scheduled jobs on deactivation. Never require `DISABLE_WP_CRON`.

### G. Frontend

- **Product:** Interactivity API and ES modules. No jQuery on the frontend.
- All frontend data goes through one shared REST client that refreshes nonces. No scattered raw `fetch()`.
- No inline `<script>`, `<style>` or `onclick`. No browser `alert()` / `confirm()` / `prompt()`; use a toast and a confirm modal.
- Plugin pages register a real template (`template_include`). Never hide the theme's header and footer with CSS.

### H. Free / Pro boundary (products)

- Free works fully without Pro.
- Pro loads after Free, checks Free is active, and talks to Free **only through hooks and Free's published contracts**. If Pro needs something, add a hook in Free.
- Pro's options, meta, tables, actions and cron hooks are prefixed `{plugin}_pro_`.

### I. Never break live sites

- Never remove a public function, hook, route, option, meta key, capability or template in the same release that deprecates it. Deprecate first with `_deprecated_function()` / `_deprecated_hook()`.
- Renames keep an alias for the old name. A change to default behaviour ships with a filter to restore the old behaviour.
- How long deprecated and renamed items are kept: Product manual P5-E.
- **Patch** releases are fixes only, with no schema changes. **Minor** releases add. **Major** releases may remove.
- Supported PHP: what the product readme says (`Requires PHP`). A deprecation notice on any supported version is a bug.

### J. Translation

Every user-facing string is translatable with the plugin slug as text domain, with `/* translators: */` comments and numbered placeholders. `wp i18n make-pot . languages/<slug>.pot` must give zero warnings.

---

## D6. UI Rules

### Design tokens

- **No raw hex colours or px values in component CSS.** Use the product's tokens (`var(--{prefix}-*)`), which chain to the theme's colours (`var(--wp--preset--color--primary, #3B82F6)`). Hex only in the token block.
- Spacing scale 4px-48px (card padding and grid gap 20px, form field gap 12px). Type 11px-32px. Radius 4/8/12/16px.
- Build from the shared building blocks: page shell, card, button (primary / secondary / ghost / danger; heights 32 / 40 / 48px), input (40px), badge, empty state (icon, title, text, action). **Never a bare "No items found."**

### Breakpoints

- Mobile ≤ 640px, tablet 641-1024px, desktop ≥ 1025px. Two media blocks, at the bottom of the file. `:hover` styles inside `@media (hover: hover)`.
- Every card: test at **1440px and 390px** (D7-G). When the change touches layout or breakpoints, and in release Tier 1, also **768px and 1024px**. Admin pages at 390px too. No horizontal scroll, no clipped controls.
- **Tap targets at least 40px** (34px only on dense admin list rows).

### Accessibility (WCAG 2.1 AA)

- Contrast 4.5:1 for text, 3:1 for large text and UI elements.
- Visible `:focus-visible` outline (2px accent, 2px offset). Never `outline: none` without a replacement.
- Keyboard: Tab follows reading order, Enter/Space activate, Esc closes, arrows move inside groups.
- `aria-label` on icon-only buttons. Loading: `aria-busy` + `aria-live="polite"`. Field errors: `aria-invalid` + `aria-describedby`, shown at the field.
- Modals: `role="dialog" aria-modal="true"`, focus trapped inside and returned on close.
- Motion over 150ms respects `prefers-reduced-motion`.

### Dark mode & RTL

- Dark mode overrides tokens at the root only, never per component. Dark colour pairs must also pass AA.
- RTL: logical properties (`margin-inline-start`, `padding-inline-end`, `text-align: start`). Ship an `-rtl.css` file. A missing RTL file blocks the release.

### Icons

One icon set per product (Lucide for new work), stored locally. No emoji, no icon fonts, no Dashicons in new code.

### Admin pages

Each admin page is one of: **Settings** (sidebar + cards), **Dashboard** (stat tiles), **List table**, **Editor**, **Wizard**, **Meta box**. Sidebar for 3+ sections; tabs only for 2. Branded header with name, version and one primary action. Hide other plugins' notices on our pages.

### States

Every view handles **loading, empty, error and success**. A failed save rolls back the UI and shows an error.

### Theme fit (products)

Frontend screens are checked under our own themes (BuddyX, Reign) **and** a default theme (Twenty Twenty-Four), light and dark. Fonts and accent colours come from the theme. Buttons styled from `<a>` set explicit hover, visited and focus colours, because themes override them.

---

## D7. Self-Checks Before Review

Run these on what you changed before you open the PR. They catch the bugs QA bounces most often.

### A. Wiring check: every button connects to a handler

```bash
# 1. Interactive elements in templates
grep -rnE 'data-action=|data-nonce=|wp_nonce_field\(|wp_create_nonce\(|name="action"' templates/ includes/
# 2. JS bindings and calls (source, not minified)
grep -rnE "addEventListener\(|\.on\(\s*['\"](click|change|submit)|action\s*:\s*['\"]|/wp-json/|X-WP-Nonce|nonce\s*:" assets/js src --include=*.js | grep -v '\.min\.js'
# 3. PHP handlers
grep -rnE "wp_ajax_(nopriv_)?|admin_post_|register_rest_route|check_ajax_referer|wp_verify_nonce" --include=*.php .
```

Cross-check:
- Every button or selector has a JS handler. Otherwise it is an orphan button.
- Every JS action has a PHP handler. Otherwise the call returns `0` or `-1`.
- Every PHP handler has a caller. Otherwise it is dead code; remove it.
- The **nonce action name and parameter key** match in template, JS and PHP.
- Every field the JS reads (`data.foo`) exists in the PHP response.
- Look for near-miss typos: `couse_` vs `course_`, hyphen vs underscore, singular vs plural.

### B. Contract check: every saved value is used

For every option, meta key and hook you touched, search the exact key across the plugin **and** its Free/Pro pair:

| Finding | Meaning | Fix |
|---|---|---|
| **Read, never written** | Feature silently runs on defaults | Point the read at the writer's key |
| **Written, never read** | Dead data | Remove it, or document the outside consumer |
| **Two keys for one thing** (`_revisions` / `_max_revisions`) | Values drift apart | One key, one helper |
| **Hook listened to, never fired** | Code never runs | Fix the name, or fire it |
| **Same setting resolved in two places** | Different defaults | Route through the one getter |
| **Same access rule written per surface** | Nav, form and REST disagree | One shared check |

Static search only finds candidates. **Prove a setting works by turning it OFF and ON in the browser and seeing the behaviour change.**

### C. Security sweep

```bash
grep -rn '\$wpdb->\(query\|get_\)' . | grep -v prepare
grep -rnE 'echo\s*\$_|print\s*\$_|<\?=\s*\$' . | grep -v esc_
grep -rn '\$_\(GET\|POST\|REQUEST\)\[' . | grep -vE 'sanitize_|absint|intval|wp_unslash'
grep -rnE '\beval\(|create_function|unserialize\(|call_user_func.*\$_|(include|require).*\$_' .
grep -rn register_rest_route . | grep -v permission_callback ; grep -rn "__return_true" .
grep -rnE 'var_dump|print_r|error_reporting|display_errors' .
```

Then confirm by hand that every write handler checks the capability before the nonce.

### D. Performance sweep

```bash
grep -rnE "posts_per_page.*-1|numberposts.*-1|query_posts\(|session_start\(|setInterval.*(fetch|ajax)" .
grep -rn "update_option\|add_option" . | grep -v "admin\|activate"
grep -rn "wp_remote_get\|wp_remote_post" .
```

Look for queries inside loops and `LIKE '%...'`. Measure the same URL before and after with Query Monitor. Seed realistic data first: 1,000+ posts, 500+ users (`wp post generate`, `wp user generate`).

### E. Standards

- `php -l` on every changed file
- `vendor/bin/phpcs` (WordPress standard, repo's `phpcs.xml.dist`): zero errors
- `vendor/bin/phpstan analyse`: no new issues. **Never silence an error with an ignore comment or by adding it to the baseline to get green.**
- Unit tests for the area you touched: `vendor/bin/phpunit tests/<Area>/`

### F. WordPress.org / Plugin Check (products)

Run `wp plugin check` on the **built zip** (D10), not the working folder. Forbidden: `eval`, `create_function`, backticks, `goto`, short open tags, `ini_set`, `set_time_limit`, `wp_redirect`, CDN-loaded core assets, inline `<script>`/`<style>`. `uninstall.php` removes the plugin's data.

### G. Browser check (the one that matters most)

**Static checks mostly re-prove what the commit hook already proved. The browser check is what actually catches defects on a fix.**

- Every surface you changed, at **desktop (1440px) and 390px**, in **light and dark**.
- As **each role that can reach it**: logged out, member who owns the item, a second member who doesn't, moderator/editor, admin (D9 role ladder).
- Zero console errors, no new debug.log lines.
- Empty, loading and error states.
- For interactive pages, test after a client-side navigation as well as a full page load.
- **Look at the screenshots.** Clipped, invisible or wrong-colour elements pass every automated check.
- Generated output (emails, PDFs, exports): produce it and read it.

---

## D8. Quality Gates: Commit, Push, Card, Release

Gates are **tiered**. Run what your change can break on each fix. Run the full battery once per release. Running the release battery on every card costs more than it catches, and that cost is what makes people start skipping gates altogether.

### Gate 1: Every commit (pre-commit hook)

- Lints **staged files only**, so it stays fast: `php -l`, PHPCS and quick static checks (seconds, not minutes).
- Enable it once per clone: `git config core.hooksPath .githooks` (repos with a `composer.json` script do this on `composer install`).
- `git commit --no-verify` is for emergencies only, and you say so in the PR.

### Gate 2: Every push and pull request (CI)

Every change reaches `main` through a pull request. CI runs the same checks a reviewer would. A typical product pipeline:

| CI job | What it proves |
|---|---|
| PHP lint across every supported PHP version (e.g. 8.1-8.4) | No syntax that breaks on an older or newer PHP |
| PHPCS (WordPress standard) | Coding standards |
| PHPStan | Type and logic errors |
| PHPUnit (WordPress integration, real database) | Business logic still works |
| Browser journeys on seeded data | Key user flows still work end to end |
| Docs and routing checks | Docs config matches the files; admin links resolve; documented hooks exist |
| Project-specific checks (D8-E) | The rules this product has learned the hard way |

- **Red CI = no merge.** "No checks ran" is also red.
- `main` is protected: PR required, checks must pass, no force-push.
- **Private / paid repos** (CI turned off on purpose): run the same checks locally with the repo's check script (e.g. `bin/check.sh`) and paste the result in the PR.
- **Client projects:** same idea, sized to the project. At minimum PHP lint, PHPCS and a PR review before merging to `develop`.

### Gate 3: Every card, before Ready for Testing

Run **what your change can actually break**:

| You touched | Run |
|---|---|
| Any PHP | Pre-commit gate (already automatic) |
| PHP logic that has tests | The tests for that area, not the whole suite |
| CSS | The UI checks (tokens, tap targets, breakpoints) |
| REST / frontend data | Wiring check (D7-A) + REST boundary check |
| Options, meta, hooks | Contract check (D7-B) |
| **Any member- or owner-facing UI** | **Browser check (D7-G). Not optional, not deferrable.** |

### Gate 4: Every release (the full battery)

Run the full check script and the build script without shortcuts. The build script **refuses to produce a zip** if any of these fails:

- Full lint + PHPCS + PHPStan + full unit suite
- Browser journey suite, with no regressions against the saved baseline
- Behavioural checks on a live test site (settings applied, roles enforced, flows complete)
- **Docs truth:** the inventory (manifest) and `CAPABILITIES.md` were updated **after** the last code change, and no feature still says "coming soon"
- The QA report (D10) is for this version and newer than the last code commit

**Skipping a gate must be deliberate.** Every bypass is a typed, named switch (e.g. `SKIP_JOURNEY_RUN=1`), stated in the commit message with the reason. A gate that quietly skips itself because a machine wasn't set up is worse than no gate. It looks green and proves nothing.

### D8-E. Grow your own checks

Every product collects small check scripts for the mistakes it has made. Any plugin or client project can add the same kinds:

- No `admin-ajax` on the frontend (REST only)
- Tap targets at least 40px; only token colours and no raw hex
- Icons come from the one icon set; no inline scripts in admin PHP
- Admin tabs check capabilities; admin links and routes resolve
- Cross-plugin guards (Pro never calls Free internals)
- Docs config matches the docs folder; every documented hook exists
- Personal-data export and erase cover every table that stores user data
- Every cache write has an invalidation path
- Option defaults match between code and docs

**Rule:** when the same kind of bug reaches QA twice, write a check for it and add it to the check script. Known, reviewed exceptions go in a **baseline file with a reason for each**. Only **new** errors fail the gate.

---

## D9. QA of a Card

The steps are the same whether QA or a developer verifies the card.

### A. Know the product first (once per product)

- **Owner's view:** every option and its default, admin page, template, email and hook the site owner can see or change. Look for blank defaults, options with no admin screen, readme promises with no code behind them.
- **Core paths:** the 10-15 flows that make up most real use, ranked from the readme, the first settings screen and past bug hotspots. Confirm the list once with the product owner.
- **Role matrix:** what each role should and shouldn't be able to do, taken from the capability code.
- **Test accounts:** at least **two members with the same role** (an owner and a non-owner of an item), plus each elevated role. With only one account, every ownership check passes by accident.

### B. Each session

Walk the core paths first. **A broken core path outranks every card in the column.**

### C. Each card

1. **Treat the card as a claim, including its "Fixed" comment.** If you can't verify it, the verdict is BLOCKED, not PASS.
2. List every surface the behaviour lives on (D2-D). A fix on one surface with broken siblings is a BOUNCE.
3. Check the card's history. Has this module bounced before?
4. **Reproduce the original problem on the old code first, then test the fix.** On a shared site you can do this without checking out old code: re-apply the old CSS in the browser, flip a filter for one request, or wrap data changes in a transaction you roll back. **No failure seen = no PASS.**
5. **Walk the role ladder in this order:**
   1. the reporter's role
   2. logged out
   3. member who owns the item
   4. **a second member who doesn't own it** (permission bugs live here)
   5. moderator / editor
   6. admin, last and never alone. Admin bypasses every gate, so a permission fix confirmed only as admin is not confirmed.
6. Check every touched surface at 1440px and 390px, light and dark, logged in and out, empty/loading/error states, zero console errors. Frontend: our themes + one default theme.
7. Check side effects: emails arrive with the right subject and body (a "sent" log line is not delivery); data values before and after.
8. Before believing a "no", rule out test traps: cached redirects, the wrong role, background jobs not run yet, content rendered by JS that isn't in the page source.
9. Put back every setting you changed, and say so in the verdict.

### D. The five questions (any "no" = bounce)

1. Does the original problem still reproduce? (Must be **no**, and you must have seen it fail first.)
2. Does the fix work the way it says it does?
3. Were all the other places it lives checked?
4. Would both the site owner and the end user call it fixed?
5. Is there a regression guard (test or checklist step)?

### E. Classify before judging (stop at the first yes)

1. Breaks a stated behaviour or contract → **defect**. Bounce, no debate.
2. Breaks a published standard (WCAG AA, 40px tap target, etc.) → **UX expectation**. Cite the standard.
3. The owner can't find, control or trust it → **owner expectation**.
4. Otherwise → **preference**. Not a bounce. Note it as a suggestion.

**Developer pushback on a preference bounce:** reproduce it at the exact viewport, judge it as the site owner and the customer would, cite a published reference, and offer a filter if it's genuinely subjective. Move it back to Ready for Testing with the reason. Functional bugs are never negotiated.

### F. Verdict comment

```
<one plain sentence: what happens, to whom, why it was missed>
VERDICT: PASS | BOUNCE | BLOCKED | CANNOT-REPRO | NEEDS-INFO | NOT-A-BUG
Build: <product/project> @ <commit or version>   Env: <site, WP, PHP, theme>
Triage: reach / impact / location -> P0-P3
Class: defect | ux-expectation | owner-expectation | preference
Roles walked: logged-out | owner | second member | moderator | admin
Q1-Q5: <answers>
Evidence: <screenshots of the failing and the working state, commands, before/after>
Not covered: <never empty by default>
Check added: <new checklist line or test> | none (why)
```

### G. Moving the card

| Verdict | Move to |
|---|---|
| PASS | Done (products) / Ready for Deployment (client projects, Agency manual 4A) |
| BOUNCE | Bugs, with repro steps |
| NOT-A-BUG | Done (closed), with the evidence and the standard cited. Never trash it |
| Partly done | Done (Ready for Deployment on client projects) for what shipped; new card in Scope for the rest |
| CANNOT-REPRO / NEEDS-INFO / BLOCKED | Stays, reporter @mentioned with the specific question |

After moving, re-open the card and check it is really in the new column.

**A finding needs four things** to be a bounce or a new card: **where** (surface, role, config, URL), **why it's wrong** (contract or standard), **who it costs**, and a **fix pointer** (similar code that already does it right). Without all four it is a comment. Problems found outside the card get their own cards.

**Every bounce adds a check:** a new line in the product's QA checklist, in plain words and tagged with the card, plus a regression test where possible.

---

## D10. Release QA & Release Steps

**Client project:** use the deployment process in Agency manual Section 16, with the same QA tiers below scaled to the change. The steps below are for products.

### A. Release QA tiers (in priority order)

The browser tiers decide the release. Code checks never replace them: in one release cycle all 17 QA bounces were presentation or flow, and static analysis caught none of them.

| Tier | Covers |
|---|---|
| **0 Boot** | Activates cleanly, assets built, migrations safe to run twice, debug.log clean for the whole run |
| **1 Presentation & flow** (main gate) | Core flows per role, theme fit, every block renders and its settings change the output, server-rendered and JS-rendered items look identical, UI states, accessibility, zero console errors, at 1440, 1024, 768 and 390px |
| **2 Completeness** | Click everything (no dead buttons or tabs), three entry points, Free-only and Free + Pro states, settings where owners expect them |
| **3 Logic** | REST live, money exact to the cent, roles enforced, background jobs run, two users at once, scale, notifications fire exactly once, external API down handled, time zones |
| **3E Environment** | Minimum WP/PHP, multisite, object cache, page cache, conflict plugins (Elementor, Yoast, Rank Math, LiteSpeed, WooCommerce, BuddyPress), Chrome / Firefox / Safari iOS |
| **4 Contract & wiring** | D7-A and D7-B on the whole product, permission check on every write |
| **5 Code quality** | Gate 4 battery (D8) |
| **6 i18n, docs, packaging** | `.pot` up to date, docs updated, zip contents, privacy exporter/eraser |

A step marked SKIPPED without a written reason counts as **FAIL**. Every pass needs something you actually saw on screen or in the database. A clean log alone is not a pass.

### B. Smoke checklist sections (same letters in every product)

- **A Fresh install:** activates, tables created, first page loads, deactivate/reactivate creates no duplicates
- **B Upgrade:** install the **previous released zip**, add real data, upgrade to the new zip. No fatal, DB version updated, data shows on every surface, settings not reset, scheduled jobs re-registered, no new log lines
- **C Core flows** per role (at least 10 passes)
- **D Regression guards:** one row per customer-visible fix from earlier releases
- **E Pro / add-on features**
- **F Cross-browser:** 5 key pages on Chrome, Firefox, Safari iOS
- **G First 48 hours** after release

A full manual walk takes about 90 minutes, plus about 45 minutes for the release checklist.

**Test site:** mirror a real customer. Our theme (not a default block theme), the full Free + Pro + integrations set active, an object cache, realistic seeded data (1,000+ rows, 500+ users).

### C. Must pass before release

- Zero failures and zero new debug.log entries
- QA report version = release version, and the report is newer than the last code commit (in both repos of a Free/Pro pair)
- Free/Pro pairs: one Free-only walk and one Free + Pro walk
- **Hard fails** (block on their own): fatal or JS error, save not kept, permission or privacy leak, data loss, a readme promise that isn't true
- **Soft issues** (layout, wording, contrast): argued on the card

**When something fails:** stop, don't merge. A second person reproduces it. File a Bugs card with the failed row word for word, the environment, browser and role. Fix it on the release branch, then re-walk that whole section.

### D. Release steps (in order)

1. **Branch:** `release/X.Y.Z`. `git status` clean, up to date, `main` merged in.
2. **CI green** on the PR into `main` (or the local check run for private repos).
3. **Pre-release gates:** Gate 4 battery (D8), wiring + contract check, REST routes return no 5xx and all have permission checks, a security sweep compared with the last tag (findings written to `audit/security/<version>.md`), docs truth.
4. **Version bump: every location must match**, or WordPress loops on updates:
   - plugin header `Version:` (or `style.css` for themes)
   - the version constant / property in the main file
   - `readme.txt` `Stable tag:`
   - `package.json` and `composer.json` `version` (if present)
   - Pro's version constant (same version as Free, Product manual P7)
   - any product-specific config holding the version

   Never downgrade a version.
5. **Changelog** in `readme.txt` under `== Changelog ==`, in the Product manual P8 format. Update `Requires at least`, `Tested up to`, `Requires PHP`, and the upgrade notice if behaviour changes.
6. **Build the zip** with the repo's build script only (`bin/build-release.sh`, `grunt dist` or the documented equivalent).
   - **Excluded:** `.git`, `.github`, `node_modules`, `tests`, `bin`, `docs`, `audit`, `plan`, dev config files, stray `.md` files.
   - **Included:** main file, `readme.txt`, `languages/*.pot`, includes, assets (source + minified + RTL), templates, runtime libraries.
   - Anchor exclude patterns to the plugin root. An unanchored `src` once stripped bundled libraries and broke licensing on every install.
   - The zip extracts to a folder named exactly `<slug>/`. Investigate if it is more than twice the size of the last zip.
7. **Plugin Check on the built zip:** `wp plugin check <zip> --severity=error`. No new errors in our code.
8. **Clean install test on a fresh WordPress (never skipped, not even for hotfixes):** activates with the new version, home page loads, no fatal or text-domain notices in debug.log, plugins page + one admin screen + one frontend screen look right. Pairs: deactivate Free, and Pro shows a "requires Free" notice instead of crashing.
9. **Go / No-go:** written Go from the Product Owner on the Basecamp release card (Product manual P7). No Go, no merge or tag. Release timing rules (no Friday after 3 PM, no open P0/P1) are in P7.
10. **Merge** the release PR after CI is green again. Never push to `main` directly.
11. **Tag** `vX.Y.Z` (annotated) on `main` after the merge, and only when `main` is green. Then merge `main` back into `develop` through a PR.
12. **GitHub release:** attach the zip. Title `Product X.Y.Z - one-line summary`. Body = the readme changelog bullets.
13. **Free/Pro lockstep** (rule: Product manual P7): same version, released together, each release links the other.
14. **Announce** in `#releases`. A version counts as available to customers only after the release lead confirms it there.
15. **First 48 hours:** debug.log clean on the test site, scheduled jobs present, no "broke after update" tickets. Each Feature Owner watches their feature.

---

## D11. Basecamp Conventions & Evidence

### Standard card table (every product and client project)

| Column | Holds |
|---|---|
| **Triage** | New, not yet looked at |
| **Not now** | Parked on purpose, with a reason |
| **Scope** | Agreed work or accepted feature requests waiting to be planned |
| **Suggestions** | Ideas and preference feedback, not committed |
| **Possible Bug** | Reported, not yet reproduced. Empties after every QA session |
| **Bugs** | Reproduced. Includes bounces from QA |
| **Ready for Development** | Root cause known, fix direction clear, owner assigned |
| **In Development** | Being built |
| **Ready for Testing** | Merged, self-checked, browser-checked, handover comment posted |
| **In Testing** | QA working on it |
| **Done** | Products: verified by QA (or closed as not-a-bug with evidence). Client projects: client confirmed it on live |

- **Client project:** In Testing → **Ready for Deployment** → **Deployed** → Done (Agency manual Section 4A).
- **Blocked** cards stay in their column and are put **On Hold** with a comment saying what they are waiting for and from whom.
- Released / deployed version numbers are recorded in a card comment.

### How we write on cards

- **Nothing is done until it is on the card.** Coordinate on the card, not in Slack. Slack is for quick questions and internal discussion (client projects: `#proj-[client]`).
- **Every comment stands on its own** for someone picking it up cold: steps, role, configuration, evidence, what remains.
- Basecamp comments render HTML, not Markdown. Use `<strong>` and `<br>`.
- Developer handover comment: commits, retest steps, surfaces, roles and viewports covered, not covered.
- QA verdict comment: D9-F.
- Code review comment: Verified / Affected files / Root cause / Suggested fix / Branch reviewed.
- Agree a prefix for test data (e.g. `QA-RFT ...`) and announce temporary setting changes on the card.
- **Client project:** card comments are client-visible. Keep internal discussion in `#proj-[client]` (Agency manual 2B), and keep comments client-friendly.

### Evidence

- Screenshots of the **failing state and the working state**, at 1440px and 390px, labelled with **role + viewport**.
- Keep screenshots outside the site's web root (never in `wp-content/` or the site's public folder). Attach what must be kept to the card.
- Acceptance checklist on bug cards: reproduced (or rejected with evidence) / root cause found / fix shipped or workaround sent / customer or client told / ticket updated.

---

## D12. Replying to Customers & Clients

**Client project:** the PM replies to the client (Agency manual 2B). Developers give the PM the facts below.

- **Reproduce before replying.** A draft written before reproducing is thrown away.
- **Reply and fix targets:** Product manual P9 and the release cadence in P7 (products); Agency manual Sections 2B and 9B (client projects). A useful reply means reproduced, a workaround, an honest next step. It is not time to fix.
- **Never promise a date.** Say "in the next update."
- **Structure:** greeting → one line naming their exact issue → the fix or numbered next steps → one detail that prevents the next back-and-forth → what happens next.
- Confirmed bug: *"Thanks for the detailed report - I've reproduced [issue] and logged it for a fix. For now, [workaround]. I'll follow up here once the fix ships."* If it was our regression, start with a short apology.
- Rate your own confidence 1-10 in the internal note: 9-10 = reproduced on released code, cause confirmed. 5-6 = add caveats or ask for the missing detail. **1-4 = don't send.**
- **Never:**
  - ask the customer to debug, deactivate plugins or switch theme on a **live** site
  - ask a free user for login details
  - call something a bug you haven't reproduced
  - say "feature X doesn't exist" without searching PHP, JS, templates and REST at the released version and checking the browser
  - send placeholders, dev jargon or code to a non-developer
  - offer free custom work
- When the fix ships: reply "fixed in vX, please update", add a private note, close the ticket.
- **Aging:** a card with no useful reply 48 hours after carding is stale (waiting in the normal release cycle is not stale). Post an aging alert on the card and in the product channel (`#prod-[product]`), at most once a day: `[Aging Alert - Day N] Priority / Customer / Product / ticket #... - please update or pick this up.`

---

## D13. Documentation

- Product docs live in the repo under `docs/website/`, in Markdown, committed with the code. Docs fixes go into the repo, never directly into the website.
- Folder shape: `docs_config.json` (sections and page order), `images/`, then sections such as `getting-started/`, `settings/`, `developer-guide/`, plus `faq/` and `troubleshooting/` (both required).
- **Order pages the way people use the product**, never alphabetically: overview → install → setup → first use → features → settings → integrations → Pro → developer → FAQ → troubleshooting → what's new.
- Name pages after what the user wants to do ("Run a poll"), not internal names. Free and Pro are one set of docs with Pro as a section, and Pro pages carry a `**PRO**` label.
- Every page has exactly one H1, headings never skip levels, and no two pages share a title. Every section has a one-line description.
- Images are `.webp` or `.svg` in `docs/website/images/`, with relative links and alt text. They show realistic content, not test data or empty screens.
- No placeholders, no em-dashes, no internal tool names or card numbers.
- Update docs in the **same PR** as the behaviour change (Product manual P12).

---

## D14. Repo Setup Checklist

Every product repo should have these. New repos start with them; older repos add them when they're next released.

| Path | Holds |
|---|---|
| Project guide (repo root, READ-FIRST) | Conventions, architecture, file placement, how to run the gates |
| `CAPABILITIES.md` | What the product does, buyer-level, with file:line |
| `audit/manifest.json` | Inventory: routes, tables, options, hooks, capabilities, blocks, cron, CLI |
| `audit/ROLE_MATRIX.md` | What each role may and may not do |
| `.githooks/pre-commit` | Gate 1 (staged files) |
| `bin/check.sh` | Gate 2/4 checks, runnable locally, same as CI |
| `bin/build-release.sh` | Builds the zip; refuses on failed gates |
| `.github/workflows/ci.yml` | CI (public repos) |
| `phpcs.xml.dist`, `phpstan.neon.dist`, `phpunit.xml.dist` | Tool config |
| `docs/qa/PRE_RELEASE_SMOKE.md` | The A-G manual walk |
| `docs/qa/QA_RELEASE_CHECKLIST.md` | Versions, packaging, install, upgrade, tag |
| `docs/qa/qa-config.json` | Personas, themes, blocks, key URLs, Free/Pro pair, readme promises, known issues |
| `docs/qa/` last-pass report | Result of the last walk: version, date, pass/fail per section, untested items with reasons |
| Baseline files | Reviewed exceptions for each check, each with a reason |
| `docs/website/` | Customer docs (D13) |

**Client project:** a project guide, `phpcs.xml.dist`, a pre-commit hook, and a short QA checklist for the client's core flows are the minimum.

---

## D15. What Does NOT Count as Tested

None of these count as a pass. If one is all you have, write the item down as **untested, with the reason**:

- "Too small to test", "only CSS", "same as last release", "will cover later"
- "I read the code"
- "Admin sees it fine"
- HTTP 200, the element exists in the page, a clean search result, or green PHPCS/PHPStan
- A log line saying an email was "sent"
- A fix checked on one surface when the behaviour lives on several
- A test that never failed against the unfixed code

And:

- **"Not covered" is never empty.** A claim of total coverage is the least trustworthy kind.
- **Never test risky changes on a customer's live site.** Use staging or a test site.
- **A search that finds nothing may be the wrong search.** Try another spelling or pattern before concluding.
- **Never trust a card column, a note or a version header over the live code and the reporter's actual words.**

---

## Document Control

- **Owner:** Lead Developers + QA Lead
- **Version:** 1.0
- **Last Updated:** October 2026
- **Next Review:** January 2027
- **Change rule:** when a bounce, escaped bug or hotfix shows a missing step, add it here in the same week.

© 2026 WBCOM DESIGNS. All Rights Reserved.
