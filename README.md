# Liberty Tax Help Center Announcements
**Dynamic Announcement Banners for Support Central**

---

## 📢 What This Is

This repository contains the **announcement banners** that appear on the Liberty Tax Help Center home page. These are the info boxes at the top of https://supportcentral.libertytax.net/hc/en-us that notify users about:

- System issues and outages
- Product updates and features
- Important deadlines
- Login problems
- Process changes

**Testing the pipeline (theme fetch, smoke banner, troubleshooting):** see [`TESTING_AND_DEBUG.md`](TESTING_AND_DEBUG.md).

---

## 🚀 Quick Start

### Adding a New Announcement

1. **Edit `announcements-us.html`** (US) or `announcements-ca.html` (Canada)
2. **Add your banner** using the template below
3. **Commit:** `git commit -am "Add [topic] announcement"`
4. **Push:** `git push origin main`
5. **Wait 2-5 minutes** for deployment
6. **Verify** at https://supportcentral.libertytax.net/hc/en-us (US) or https://supportcentralcanada.libertytax.net/hc/en-us (Canada)

**That's it.** No PR required. No feature branches. Just edit, commit, push.

---

## 📝 Banner Templates

### Blue Info Banner (Standard)

```html
<!-- PRIORITY X: Category - Active -->
<!-- Topic: Brief Description | Added: YYYY-MM-DD | Article: [ID] -->
<div style="background-color:#42a5f5; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    Your announcement text here. Read more 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/[ARTICLE-ID]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Use for:** Product updates, general info, tips, reminders

---

### Red Urgent Banner (Critical)

```html
<!-- PRIORITY X: Category - Active -->
<!-- Topic: Brief Description | Added: YYYY-MM-DD | Article: [ID] -->
<div style="background-color:#FF0000; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    URGENT: Your critical message here. Read more 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/[ARTICLE-ID]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Use for:** Critical issues, outages, security alerts, urgent deadlines

---

## 🔢 Priority System

Announcements display **top to bottom** by priority:

- **Priority 1-2:** Critical issues, system outages, widespread impact
- **Priority 3-4:** Feature updates, access issues, moderate impact
- **Priority 5+:** Tips, reminders, informational, long-term deadlines

**Higher priority = closer to top of page**

---

## 💡 Real Example (October 2025)

### Azure Performance Issue Added

```html
<!-- PRIORITY 1: Critical Performance Issue - Active -->
<!-- Topic: Microsoft Azure Performance | Added: 2025-10-29 | Article: 35964751710999 -->
<div style="background-color:#42a5f5; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    Potential performance issues related to Microsoft Azure. Read more 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/35964751710999-Potential-performance-issues-related-to-Microsoft-Azure" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Workflow:**
1. Edited `announcements-us.html` directly
2. Added at top (Priority 1 - infrastructure issue)
3. Committed: `git commit -am "Add Azure performance issue announcement"`
4. Pushed: `git push origin main`
5. Live in 3 minutes ✅

---

## 📋 Maintenance Checklist

### Weekly
- [ ] Remove resolved/outdated announcements (archive them first!)
- [ ] Verify all links still work
- [ ] Adjust priorities if needed

### Monthly
- [ ] Review color choices (still appropriate?)
- [ ] Check mobile display
- [ ] Verify accessibility (contrast, link text)
- [ ] Review archive files for patterns/trends

### As Needed
- [ ] Add urgent announcements immediately
- [ ] Update text when situations change
- [ ] Reorder based on priority
- [ ] Archive removed announcements

---

## ✅ Pre-Push Checklist

Before every `git push`:

- [ ] HTML syntax is valid (no broken tags)
- [ ] Link URL is correct
- [ ] Text is clear and error-free
- [ ] Tracking comment is complete
- [ ] Priority order makes sense
- [ ] Color is appropriate (blue info vs red urgent)

---

## 🚨 When to Use Red vs Blue

### Blue Banner (#42a5f5) - Most Announcements
- ✅ Feature updates
- ✅ Tips and reminders
- ✅ General information
- ✅ Non-urgent process changes
- ✅ "FYI" type messages

### Red Banner (#FF0000) - Use Sparingly
- ⚠️ System completely down
- ⚠️ Critical security issue
- ⚠️ Urgent deadline (days away)
- ⚠️ Data loss risk
- ⚠️ Required immediate action

**Don't overuse red** - it desensitizes users.

---

## 📐 Tracking Comments

Always include comments above each announcement:

```html
<!-- PRIORITY [#]: [Category] - Active -->
<!-- Topic: [Description] | Added: [Date] | Article: [ID] -->
```

**Benefits:**
- Easy to find and manage announcements
- Track when added
- Quick reference to source article
- Helps with cleanup

---

## 🔗 Link Requirements

**Always link to a KB article:**
- Announcements are brief summaries
- Full details go in KB articles
- Links provide context and solutions
- Format: `https://supportcentral.libertytax.net/hc/en-us/articles/[ID]-[slug]`

**Example:**
```html
<a href="https://supportcentral.libertytax.net/hc/en-us/articles/35964751710999-Potential-performance-issues-related-to-Microsoft-Azure" style="color:#000; text-decoration:underline;">here</a>
```

---

## ♿ Accessibility

**Required:**
- Link text is descriptive (context + "Read more here")
- Color contrast meets WCAG AA (blue #42a5f5 passes ✅)
- Links are keyboard accessible (Tab to navigate, Enter to activate)
- Icon + text provide context (not color alone)

**Test with:**
- Keyboard-only navigation
- Screen reader (if major change)
- Mobile device (touch targets)

---

## 🚫 Common Mistakes

1. ❌ Forgetting `<br>` between announcements → No spacing
2. ❌ Breaking HTML tags → Page breaks
3. ❌ Wrong link URL → Users confused
4. ❌ No tracking comment → Hard to manage later
5. ❌ Using red for non-critical → Desensitizes users
6. ❌ Leaving outdated announcements → Cluttered page
7. ❌ Typos in announcement text → Looks unprofessional

---

## 🔄 How Deployment Works

1. You push to `main` branch
2. Zendesk watches this repo
3. Zendesk pulls `announcements.html`
4. Content injects into help center home page
5. **Deploy time: 2-5 minutes**

**Verify:** Visit https://supportcentral.libertytax.net/hc/en-us

---

## 📞 Emergency Protocol

**If urgent announcement needed:**

```bash
# 1. Edit file
nano announcements.html

# 2. Commit immediately
git commit -am "URGENT: [topic]"

# 3. Push immediately
git push origin main

# 4. Verify deployment (2-5 min)
# Visit https://supportcentral.libertytax.net/hc/en-us

# 5. Notify team
```

**If bad announcement deployed:**

```bash
# 1. Fix immediately
nano announcements.html

# 2. Commit fix
git commit -am "Fix: [what was wrong]"

# 3. Push fix
git push origin main

# 4. Verify fix deployed
```

---

## 🤖 For AI Assistants

### What You Can Do
- ✅ Edit `announcements-us.html` or `announcements-ca.html` directly
- ✅ Add new announcements using templates
- ✅ Update existing announcement text
- ✅ Remove outdated announcements (archive them first!)
- ✅ Reorder by priority
- ✅ Update tracking comments
- ✅ Archive removed announcements

### What You Should Ask First
- ⚠️ Verify link URLs are correct
- ⚠️ Confirm priority placement
- ⚠️ Check if red banner is truly necessary

### Quality Standards
- HTML syntax must be valid
- Links must work
- Text must be clear and error-free
- Tracking comments must be complete
- Accessibility must be maintained

---

## 👥 For Humans

### First Time Here?

1. Read this README
2. Look at `announcements-us.html` or `announcements-ca.html` to see current structure
3. Use templates above for new announcements
4. Test your HTML syntax before pushing
5. Verify deployment after push
6. Archive removed announcements for historical reference

### Need Help?

- **Technical Lead:** Steven Codling
- **Workspace Docs:** See main repo `ANNOUNCEMENT_WORKFLOW.md` for detailed workflow
- **Git Issues:** Standard Git procedures apply (commit, push, verify)

---

## 📂 Repository Info

**Repository:** liberty-supportcentral-announcements  
**Remote:** https://github.com/escosuave/liberty-supportcentral-announcements.git  
**Branch:** main  
**Files:** 
- `announcements-us.html` - US announcement banners (edit this for US)
- `announcements-ca.html` - Canada announcement banners (edit this for Canada)
- `announcements-us-archive.md` - Archive of removed US announcements
- `announcements-ca-archive.md` - Archive of removed Canada announcements
- `README.md` - This file (documentation)

**Deployment:** Zendesk auto-deploy on push to main  
**Production URLs:** 
- US: https://supportcentral.libertytax.net/hc/en-us
- Canada: https://supportcentralcanada.libertytax.net/hc/en-us

---

## 📚 Archive Files

**Purpose:** Historical record of removed announcements for auditing and reference.

**Files:**
- `announcements-us-archive.md` - US announcements archive
- `announcements-ca-archive.md` - Canada announcements archive

**When to Archive:**
- ✅ When removing expired announcements (deadlines passed)
- ✅ When removing resolved issues
- ✅ When removing outdated information
- ✅ When replacing with newer announcements

**How to Archive:**
1. Copy the full HTML block (including comments) from the active file
2. Paste into the appropriate archive file (`announcements-us-archive.md` or `announcements-ca-archive.md`)
3. Add metadata: Date removed, Reason for removal
4. Include display text for quick reference
5. Maintain chronological order (newest removals at top)

**Why Archive?**
- 📋 **Audit Trail:** Track what was shown and when
- 🔍 **Reference:** Reuse past announcements or wording
- 📊 **Compliance:** Historical record for documentation
- 🎯 **Patterns:** Identify recurring issues or topics

**Example Archive Entry:**
```markdown
### Windows 10 End of Support
**Priority:** 5 (Critical Deadline)  
**Date Added:** [Previous]  
**Date Removed:** 2025-01-30  
**Reason:** Expired deadline (deadline was 2025-10-14)  
**Article ID:** 4410646721687

[Original HTML and display text...]
```

---

## 🔍 Current Active Announcements

*Check the active announcement files for current state:*
- US: `announcements-us.html`
- Canada: `announcements-ca.html`

---

## 📝 Version History

| Date | Change | Commit |
|------|--------|--------|
| 2026-02-17 | Add known issue: Clients unable to create accounts from document upload link (US Mobile App) – Priority 1 | (pending push) |
| 2026-01-29 | Pull down office hours known issue banner (US and CA); archive entries | de8a1ea |
| 2026-01-26 | Add Drake desktop shortcut how-to banner (US only) | 58d0968 |
| 2026-01-26 | Archive Admin-from-LINK and Smart App Control OCP banners (US); renumber P2-P4 | 14982ae |
| 2026-01-26 | Add SOCi office hour delay known issue banner (US and Canada) | 1a448ff |
| 2026-01-15 | Archive MFA email delay banner (issue resolved) | bb39299 |
| 2026-01-15 | Add Microsoft service disruption MFA email delay known issue banner (Priority 1) | cb94ac9 |
| 2026-01-15 | Reactivate Smart App Control blocking OCP banner (Priority 2) | 9fa28b6 |
| 2026-01-15 | Remove Smart App Control OCP banner from active; archive for standby | c17b18f |
| 2026-01-15 | Add Smart App Control blocking OCP known issue banner (Priority 2) | 637e36d |
| 2026-01-15 | Add Schedule 1-A Input Cheat Sheet banner (Priority 2) | 874da85 |
| 2026-01-15 | Add Client Data Sheet known issue announcement (Priority 1) | c82f750 |
| 2026-01-15 | Archive 4 resolved known issue banners (Federal Rejects, invoicing, promotion codes) | fdefaf0 |
| 2026-01-15 | Add Federal Reject R0000-120 known issue announcement (Priority 4) | c48a8ae |
| 2026-01-15 | Replaced User Manager banner with Fusion AI Assistant (US & CA) | e63e5d9 |
| 2026-01-15 | Updated banner 2: Added IL to states not getting invoiced | 52ffe17 |
| 2026-01-15 | Added Federal Reject X0000-033 known issue announcement (Priority 1) | c54d8c4 |
| 2025-10-29 | Added Azure performance announcement | c36dcc2 |
| 2025-10-29 | Added README and tracking system | [current] |

---

## 🎯 Key Takeaways

1. **Simple workflow:** Edit → Commit → Push → Verify
2. **No PR needed** for standard content updates
3. **Blue for info, red for critical** (use red sparingly)
4. **Always link to KB article** for full details
5. **Track with comments** for easy management
6. **Test before push** to avoid broken HTML
7. **Deploy is fast** (2-5 minutes)

---

**Questions? See main workspace `ANNOUNCEMENT_WORKFLOW.md` for detailed procedures.**

**Need to make changes in 10 minutes or less?**  
👉 See `GITHUB_QUICK_EDIT_GUIDE.md` for direct GitHub web editing workflow

**Templates available:**
- `.github/TEMPLATE_NEW_BANNER.md` - Copy-paste banner templates
- `.github/TEMPLATE_ARCHIVE_ENTRY.md` - Archive entry format

**Ready to update? Edit `announcements-us.html` or `announcements-ca.html` and push!** 🚀

*Last updated: 2026-01-26*

