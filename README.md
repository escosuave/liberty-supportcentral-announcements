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

---

## 🚀 Quick Start

### Adding a New Announcement

1. **Edit `announcements.html`**
2. **Add your banner** using the template below
3. **Commit:** `git commit -am "Add [topic] announcement"`
4. **Push:** `git push origin main`
5. **Wait 2-5 minutes** for deployment
6. **Verify** at https://supportcentral.libertytax.net/hc/en-us

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
1. Edited `announcements.html` directly
2. Added at top (Priority 1 - infrastructure issue)
3. Committed: `git commit -am "Add Azure performance issue announcement"`
4. Pushed: `git push origin main`
5. Live in 3 minutes ✅

---

## 📋 Maintenance Checklist

### Weekly
- [ ] Remove resolved/outdated announcements
- [ ] Verify all links still work
- [ ] Adjust priorities if needed

### Monthly
- [ ] Review color choices (still appropriate?)
- [ ] Check mobile display
- [ ] Verify accessibility (contrast, link text)

### As Needed
- [ ] Add urgent announcements immediately
- [ ] Update text when situations change
- [ ] Reorder based on priority

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
- ✅ Edit `announcements.html` directly
- ✅ Add new announcements using templates
- ✅ Update existing announcement text
- ✅ Remove outdated announcements
- ✅ Reorder by priority
- ✅ Update tracking comments

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
2. Look at `announcements.html` to see current structure
3. Use templates above for new announcements
4. Test your HTML syntax before pushing
5. Verify deployment after push

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
- `announcements.html` - The announcement banners (edit this)
- `README.md` - This file (documentation)

**Deployment:** Zendesk auto-deploy on push to main  
**Production URL:** https://supportcentral.libertytax.net/hc/en-us

---

## 🔍 Current Active Announcements

*As of last update:*

1. **Azure Performance** (Priority 1) - Blue banner
2. **OCP Auto-Update** (Priority 2) - Blue banner
3. **LINK/LRC Login** (Priority 3) - Blue banner
4. **User Manager Inactivity** (Priority 4) - Blue banner
5. **Windows 10 EOL** (Priority 5) - Red banner

*Check `announcements.html` for current state.*

---

## 📝 Version History

| Date | Change | Commit |
|------|--------|--------|
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

**Ready to update? Edit `announcements.html` and push!** 🚀

*Last updated: 2025-10-29*

