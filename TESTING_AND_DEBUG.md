# Announcements system — testing and debugging

Fresh-eyes reference for the banner pipeline (GitHub HTML → Zendesk theme → Help Center home), the Node webapp, and optional desktop tooling.

---

## Architecture (high level)

```
GitHub repo                    Zendesk Help Center (browser)
─────────────────             ─────────────────────────────
announcements-us.html   ──►   home_page.hbs: fetch(raw URL)
announcements-ca.html   ──►        └──► #announcements.innerHTML

Node webapp (webapp/)   ──►   read/write same repo files (GitHub API or Git CLI)

AnnouncementsWidget     ──►   http://localhost:5100/ (AnnouncementsApi) — separate from Node webapp :3001
```

- **Production:** US theme [`liberty-supportcentral/templates/home_page.hbs`](../liberty-supportcentral/templates/home_page.hbs) and Canada theme [`liberty-supportcentral-canada/templates/home_page.hbs`](../liberty-supportcentral-canada/templates/home_page.hbs) each set `SRC` to a **raw GitHub** URL on `main`.
- **Security:** `innerHTML` is used because the HTML source is **your** repo. If untrusted parties could edit that repo, you would need to sanitize before inject.

---

## Where to change `SRC` (smoke / staging)

| Brand | Theme file | Default `SRC` file |
|-------|------------|-------------------|
| US | `liberty-supportcentral/templates/home_page.hbs` | `.../refs/heads/main/announcements-us.html` |
| Canada | `liberty-supportcentral-canada/templates/home_page.hbs` | `.../refs/heads/main/announcements-ca.html` |

For a **smoke test** without touching `main` content:

1. Create branch `announcement-smoke-test` on the announcements repo.
2. Commit only [`.github/announcement-smoke-test-sample.html`](.github/announcement-smoke-test-sample.html) as `announcements-us.html` (or copy its contents into `announcements-us.html` on that branch).
3. In a **copy** of the theme (or a Zendesk sandbox), temporarily set `SRC` to:
   `https://raw.githubusercontent.com/escosuave/liberty-supportcentral-announcements/refs/heads/announcement-smoke-test/announcements-us.html`
4. Preview home page — you should see the word **test** in a banner.
5. Revert `SRC` to `main` and delete or ignore the smoke branch when done.

**Caution:** Hosted Zendesk pages should use **HTTPS** raw URLs. `http://localhost` as `SRC` usually fails (mixed content / CORS).

---

## Minimal “test” banner HTML

See [`.github/announcement-smoke-test-sample.html`](.github/announcement-smoke-test-sample.html) for a single blue info-style block with visible **test** text (matches live banner structure).

---

## Gap checklist (quick audit)

| Area | What to verify |
|------|----------------|
| Theme vs repo | `SRC` repo, owner, branch, and filename (`us` vs `ca`) are correct. |
| Fetch failure | Browser console: `Announcements load failed` — check Network tab for 404/403/CORS. |
| Parser / hand-edit | If you use the webapp, banner comments should match patterns in `webapp/server/services/bannerService.js`. |
| Cache | URL includes `?v=` (theme version or timestamp). Hard-refresh when debugging; allow 2–5 minutes after GitHub push for production. |
| Webapp | Status page, `GITHUB_TOKEN` or Git CLI mode, `.env` in `webapp/` for Docker — see [webapp/RUNBOOK.md](webapp/RUNBOOK.md). |
| Archive | Removing live banners: pair with `announcements-*-archive.md` when you need an audit trail — see [README.md](README.md). |
| Empty Canada file | `announcements-ca.html` may be empty; home should still load (no JS error; empty `#announcements` is OK). |

---

## When fetch fails (theme behavior)

Both US and Canada `home_page.hbs` scripts show a short **user-visible** message in `#announcements` if the fetch fails, while still logging to the console. Style or copy can be adjusted in those templates if needed.

---

## Suggested test matrix

Run in order; check each box when done.

1. **Repo sanity** — Open raw URLs in a browser (should return 200 and HTML):
   - US: `https://raw.githubusercontent.com/escosuave/liberty-supportcentral-announcements/refs/heads/main/announcements-us.html`
   - CA: `https://raw.githubusercontent.com/escosuave/liberty-supportcentral-announcements/refs/heads/main/announcements-ca.html`
2. **Theme smoke** — Override `SRC` to smoke-test branch (see above); confirm **test** banner; revert `SRC`.
3. **Production parity** — On live US/CA home: Network tab → successful GET to the raw URL; DOM contains expected banner HTML.
4. **Webapp** — From `webapp/`: `npm run dev`; Status + View Banners + Preview; optional: use a fork/test repo in `.env` to avoid production repo risk.
5. **Widget (if used)** — Run AnnouncementsApi on port **5100**; open WPF widget; confirm banner list loads (widget does **not** use Node :3001 by default — see `AnnouncementsWidget/MainWindow.xaml.cs`).
6. **Regression** — After template changes: empty announcements file, one banner, multiple banners (spacing between blocks).

---

## Automated sanity commands (local)

From PowerShell (HEAD request — no full body download):

```powershell
$i = Invoke-WebRequest -Uri "https://raw.githubusercontent.com/escosuave/liberty-supportcentral-announcements/refs/heads/main/announcements-us.html" -Method Head -UseBasicParsing
"US announcements: $($i.StatusCode)"
$i2 = Invoke-WebRequest -Uri "https://raw.githubusercontent.com/escosuave/liberty-supportcentral-announcements/refs/heads/main/announcements-ca.html" -Method Head -UseBasicParsing
"CA announcements: $($i2.StatusCode)"
```

Expect **200** for both when the repo and paths are correct. Re-run after incidents.

**Last automated HEAD check:** 2026-02-19 — `announcements-us.html` **200**, `announcements-ca.html` **200** (PowerShell `Invoke-WebRequest -Method Head` against `main` raw URLs).

---

## Related docs

- [README.md](README.md) — edit / commit / push workflow for `announcements-us.html` and `announcements-ca.html`
- [webapp/RUNBOOK.md](webapp/RUNBOOK.md) — run the announcements webapp locally or in Docker
- [webapp/README.md](webapp/README.md) — API and client overview

---

## Optional follow-ups

- Point the WPF widget at a configurable API base URL if you routinely use a non-5100 port.
- Add theme CSS for `.announcements-fallback` if you want branded styling for the error state.

*Last doc update: aligned with announcements testing plan implementation.*
