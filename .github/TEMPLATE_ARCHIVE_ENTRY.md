# Archive Entry Template
**Use this when removing a banner from active announcements**

---

## Archive Entry Format

```markdown
### [Banner Topic Name]
**Priority:** [Number] ([Category])  
**Category:** [Category Name]  
**Topic:** [Full Topic Description]  
**Date Added:** [Date]  
**Date Removed:** YYYY-MM-DD  
**Reason:** [Reason for removal]  
**Article ID:** [ID]  
**Article URL:** [Full URL]

**Original Announcement:**
```html
<!-- PRIORITY X: Category - Active - US ONLY -->
<!-- Topic: [Description] | Added: [Date] | Article: [ID] (US) -->
<div style="background-color:[COLOR]; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:[COLOR]; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    [Full announcement text]
    <a href="[URL]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>
```

**Display Text:**
> [Display text only, no HTML]
```

---

## Instructions

1. **Copy** the full HTML block (including comments) from active file
2. **Paste** into archive file at top of "Archive Entries" section
3. **Fill in** metadata fields:
   - Priority, Category, Topic
   - Date Added (from comment)
   - Date Removed (today)
   - Reason (why removed)
   - Article ID and URL
4. **Add** display text (plain text version)
5. **Remove** banner from active file
6. **Commit** both changes together

---

## Common Removal Reasons

- "Replaced with [new topic] announcement"
- "Expired deadline (deadline was [date])"
- "Issue resolved"
- "Information outdated"
- "Rotated off home page to make room for higher-priority guidance"
- "No longer needed on the home page (article remains available via KB link)"

---

*See `GITHUB_QUICK_EDIT_GUIDE.md` for full workflow*
