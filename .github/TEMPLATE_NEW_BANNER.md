# New Banner Template
**Copy this template when adding a new announcement banner**

---

## Blue Info Banner (Standard)

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

**For Canada:** Replace URL with `https://supportcentralcanada.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Article-Slug]`

---

## Red Urgent Banner (Critical)

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

**For Canada:** Replace URL with `https://supportcentralcanada.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Article-Slug]`

---

## Instructions

1. **Copy** the appropriate template above
2. **Replace** placeholders:
   - `[Brief Description]` → Your topic
   - `YYYY-MM-DD` → Today's date
   - `[ID]` → KB article ID number
   - `[Article-Slug]` → Article URL slug (usually auto-filled by GitHub)
   - `[Your announcement text here]` → Your message
3. **Set Priority:** 
   - Critical issues: Priority 1-2
   - Updates/Info: Priority 3-5
4. **Insert** at appropriate position in file
5. **Renumber** other priorities if needed
6. **Commit** with descriptive message

---

*See `GITHUB_QUICK_EDIT_GUIDE.md` for full workflow*
