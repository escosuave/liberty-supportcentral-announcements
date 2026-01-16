# GitHub Quick Edit Guide
**10-Minute Emergency Changes via GitHub Web Interface**

**Purpose:** Make announcement changes directly on GitHub when Cursor/local tools are unavailable or slow.

---

## 🚀 Quick Start (5 Steps, 10 Minutes)

### Step 1: Navigate to File (1 min)
1. Go to: https://github.com/escosuave/liberty-supportcentral-announcements
2. Click on the file you need:
   - `announcements-us.html` (US only)
   - `announcements-ca.html` (Canada only)
   - Or both if needed

### Step 2: Edit File (3 min)
1. Click the **pencil icon** (✏️) in the top right
2. Make your changes using the templates below
3. Scroll down to commit section

### Step 3: Commit (1 min)
1. **Commit message:** Use format: `[Action]: [Topic]`
   - Examples:
     - `Add Federal Reject X0000-033 known issue announcement`
     - `Update banner 2: Add IL to states list`
     - `Replace User Manager banner with Fusion AI Assistant`
2. Select: **"Commit directly to the main branch"**
3. Click **"Commit changes"**

### Step 4: Verify (2 min)
1. Wait 2-5 minutes for Zendesk auto-deploy
2. Visit help center:
   - US: https://supportcentral.libertytax.net/hc/en-us
   - Canada: https://supportcentralcanada.libertytax.net/hc/en-us
3. Hard refresh (Ctrl+F5) to see changes

### Step 5: Update Tracking (3 min)
1. Edit `README.md` → Add entry to Version History table
2. If archiving: Edit archive file (`announcements-us-archive.md` or `announcements-ca-archive.md`)
3. Commit tracking updates

**Total Time: ~10 minutes**

---

## 📋 Copy-Paste Templates

### Template 1: Add New Blue Info Banner (US)

```html
<!-- PRIORITY X: Product Update - Active - US ONLY -->
<!-- Topic: [Brief Description] | Added: YYYY-MM-DD | Article: [ID] (US) -->
<div style="background-color:#42a5f5; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    [Your announcement text here]. Review the details 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Article-Slug]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Where to add:** Insert at the top (Priority 1) or appropriate priority position. Renumber other priorities if needed.

---

### Template 2: Add New Red Urgent Banner (US)

```html
<!-- PRIORITY 1: Known Issue - Active - US ONLY -->
<!-- Topic: [Brief Description] | Added: YYYY-MM-DD | Article: [ID] (US) -->
<div style="background-color:#FF0000; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#FF0000; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    Known issue: [Your critical message here]. Details and updates 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Article-Slug]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Where to add:** Usually Priority 1 (top) for critical issues. Shift existing priorities down.

---

### Template 3: Add New Blue Info Banner (Canada)

```html
<!-- PRIORITY X: Product Update - Active - BOTH BRANDS -->
<!-- Topic: [Brief Description] | Added: YYYY-MM-DD | Article: [ID] (CA) -->
<div style="background-color:#42a5f5; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    [Your announcement text here]. Review the details 
    <a href="https://supportcentralcanada.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Article-Slug]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

**Note:** Use `supportcentralcanada.libertytax.net` for Canada links.

---

### Template 4: Remove Banner (Archive First!)

**Step A: Archive the banner**
1. Copy the entire banner block (including comments) from the active file
2. Go to archive file: `announcements-us-archive.md` or `announcements-ca-archive.md`
3. Add entry at top of "Archive Entries" section:

```markdown
### [Banner Topic Name]
**Priority:** [Number] ([Category])  
**Date Added:** [Date]  
**Date Removed:** YYYY-MM-DD  
**Reason:** [Reason for removal]  
**Article ID:** [ID]

**Original Announcement:**
```html
[Paste full HTML block here]
```

**Display Text:**
> [Paste display text here]
```

**Step B: Remove from active file**
1. Delete the banner block (including comments and `<br>`)
2. Renumber remaining priorities if needed

---

## 🎯 Common Scenarios

### Scenario 1: Add Urgent Known Issue (5 min)
1. Use Template 2 (Red Banner)
2. Set Priority 1
3. Shift all existing priorities down (+1)
4. Commit: `Add [topic] known issue announcement (Priority 1)`
5. Verify in 2-5 minutes

### Scenario 2: Update Existing Banner Text (3 min)
1. Find the banner in the file
2. Edit the text inside the `<span>` tag
3. Commit: `Update [topic] banner text`
4. Verify in 2-5 minutes

### Scenario 3: Remove Outdated Banner (7 min)
1. Archive first (Template 4, Step A)
2. Remove from active file (Template 4, Step B)
3. Commit: `Remove [topic] banner and archive`
4. Verify in 2-5 minutes

### Scenario 4: Replace Banner (8 min)
1. Archive old banner (Template 4, Step A)
2. Remove old banner (Template 4, Step B)
3. Add new banner (Template 1 or 2)
4. Commit: `Replace [old topic] with [new topic] banner`
5. Verify in 2-5 minutes

---

## ⚠️ Critical Rules

### DO:
- ✅ Always commit directly to `main` branch (no PR needed)
- ✅ Use descriptive commit messages
- ✅ Archive before removing banners
- ✅ Update tracking in README.md after changes
- ✅ Test links before committing
- ✅ Verify deployment after 2-5 minutes

### DON'T:
- ❌ Create pull requests (slows down process)
- ❌ Skip archiving removed banners
- ❌ Break HTML syntax
- ❌ Use wrong article URLs (check US vs CA domains)
- ❌ Forget to update priority numbers

---

## 🔍 Quick Reference

**File Locations:**
- US announcements: `announcements-us.html`
- Canada announcements: `announcements-ca.html`
- US archive: `announcements-us-archive.md`
- Canada archive: `announcements-ca-archive.md`
- Tracking: `README.md` (Version History table)

**URLs:**
- US Help Center: https://supportcentral.libertytax.net/hc/en-us
- Canada Help Center: https://supportcentralcanada.libertytax.net/hc/en-us
- GitHub Repo: https://github.com/escosuave/liberty-supportcentral-announcements

**Colors:**
- Blue Info: `#42a5f5`
- Red Urgent: `#FF0000`

**Priority Guidelines:**
- Priority 1-2: Critical/High-Impact (red banners)
- Priority 3-4: Medium Impact (blue banners)
- Priority 5+: Low Impact (blue banners)

---

## 🆘 Troubleshooting

**Problem:** Changes not showing after 5 minutes
- **Solution:** Hard refresh (Ctrl+F5) or clear browser cache
- **Check:** Verify commit was pushed to `main` branch
- **Verify:** Check GitHub Actions/Deploy status if available

**Problem:** HTML syntax error
- **Solution:** Use templates exactly as shown
- **Check:** Ensure all tags are closed (`<div>`, `<span>`, `<a>`)
- **Verify:** No missing `<br>` between banners

**Problem:** Wrong article link
- **Solution:** Double-check article ID and domain (US vs CA)
- **Check:** Verify article exists in correct help center
- **Fix:** Edit file again, correct link, commit fix

**Problem:** Need to revert change
- **Solution:** Edit file again, restore previous content
- **Or:** Use GitHub's "View History" → "Revert" button
- **Commit:** `Revert: [what you're reverting]`

---

## 📝 Example: Complete 10-Minute Workflow

**Task:** Add new known issue banner for "System Maintenance"

1. **Navigate** (1 min): https://github.com/escosuave/liberty-supportcentral-announcements → `announcements-us.html`
2. **Edit** (2 min): Click pencil → Insert Template 2 at top → Fill in details
3. **Commit** (1 min): Message: `Add System Maintenance known issue announcement` → Commit to main
4. **Verify** (3 min): Wait 2 min → Visit US help center → Hard refresh → Check banner
5. **Track** (3 min): Edit `README.md` → Add to Version History → Commit tracking update

**Total: 10 minutes** ✅

---

**Remember:** This is content, not code. Fast, direct edits are the norm. No PR process needed.

*Last updated: 2026-01-15*
