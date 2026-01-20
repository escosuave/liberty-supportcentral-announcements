# Webapp Project Prompt for New Agent Thread
**Build a web application for managing Liberty Tax Support Central announcement banners**

---

## Project Goal

Create a simple web application that allows non-technical users to manage announcement banners for the Liberty Tax Support Central help centers without needing to use Cursor, GitHub web interface, or command-line tools. The goal is to reduce change time from 15-20 minutes to under 10 minutes with a user-friendly interface.

---

## Current System Overview

### Repository Structure
- **Repository:** `liberty-supportcentral-announcements`
- **Remote:** https://github.com/escosuave/liberty-supportcentral-announcements.git
- **Branch:** `main` (direct commits, no PR process)
- **Files:**
  - `announcements-us.html` - US help center banners
  - `announcements-ca.html` - Canada help center banners
  - `announcements-us-archive.md` - US archive
  - `announcements-ca-archive.md` - Canada archive
  - `README.md` - Documentation and tracking

### Current Workflow
1. Edit HTML file directly (via Cursor, GitHub web, or local editor)
2. Commit changes: `git commit -m "[message]"`
3. Push to main: `git push origin main`
4. Wait 2-5 minutes for Zendesk auto-deploy
5. Verify on help center

### Deployment
- Changes auto-deploy to Zendesk within 2-5 minutes after push to `main`
- No PR process needed (content updates, not code)
- US Help Center: https://supportcentral.libertytax.net/hc/en-us
- Canada Help Center: https://supportcentralcanada.libertytax.net/hc/en-us

---

## Banner Structure

### HTML Format
Each banner follows this structure:

```html
<!-- PRIORITY X: Category - Active - US ONLY -->
<!-- Topic: Brief Description | Added: YYYY-MM-DD | Article: [ID] (US) -->
<div style="background-color:#42a5f5; color:white; padding:10px 15px; border-radius:6px; font-family:Arial, sans-serif; display:flex; align-items:center;">
  <span style="background-color:white; color:#42a5f5; border-radius:50%; width:20px; height:20px; display:flex; align-items:center; justify-content:center; font-weight:bold; margin-right:10px;">i</span>
  <span>
    [Announcement text]. Details and updates 
    <a href="https://supportcentral.libertytax.net/hc/en-us/articles/[ARTICLE-ID]-[Slug]" style="color:#000; text-decoration:underline;">here</a>.
  </span>
</div>

<br>
```

### Banner Types
- **Blue Info Banner** (`#42a5f5`): Product updates, general info, tips
- **Red Urgent Banner** (`#FF0000`): Critical issues, outages, security alerts

### Priority System
- Priority 1-2: Critical/High-Impact (usually red)
- Priority 3-4: Medium Impact (blue or red)
- Priority 5+: Low Impact (blue)

---

## Webapp Requirements

### Core Features
1. **View Current Banners**
   - Display all active banners for US and/or Canada
   - Show priority, color, topic, date added, article link
   - Visual preview of banner appearance

2. **Add New Banner**
   - Form fields:
     - Brand (US / Canada / Both)
     - Priority (1-10)
     - Banner type (Blue Info / Red Urgent)
     - Topic/Title
     - Announcement text
     - KB Article URL or ID
     - Date added (auto-fill today)
   - Generate HTML from form
   - Preview before committing

3. **Edit Existing Banner**
   - Load banner data into form
   - Update text, priority, links
   - Maintain tracking comments

4. **Remove/Archive Banner**
   - Move banner to archive file
   - Add removal metadata (date, reason)
   - Update active file

5. **Reorder Priorities**
   - Drag-and-drop or up/down buttons
   - Auto-renumber priorities
   - Maintain proper spacing

6. **Archive Management**
   - View archived banners
   - Search archive by date/topic
   - Reference past announcements

### Technical Requirements

#### GitHub Integration
- **Authentication:** GitHub Personal Access Token or OAuth
- **API:** GitHub REST API or GitHub.js library
- **Operations:**
  - Read file contents
  - Update file contents
  - Commit changes
  - Push to `main` branch
  - Handle merge conflicts gracefully

#### Technology Stack Suggestions
- **Frontend:** React, Vue, or vanilla JS (simple UI)
- **Backend:** Node.js/Express or serverless (Vercel, Netlify Functions)
- **GitHub API:** @octokit/rest or github-api
- **Storage:** No database needed (GitHub is source of truth)
- **Deployment:** Vercel, Netlify, or similar

#### Security Considerations
- Store GitHub token securely (environment variables)
- Validate all user inputs
- Sanitize HTML to prevent XSS
- Rate limiting for GitHub API calls
- Error handling for API failures

### User Experience Goals
- **Simple:** Non-technical users can use it
- **Fast:** Complete changes in under 10 minutes
- **Safe:** Preview before deploying
- **Reliable:** Handle errors gracefully
- **Clear:** Visual feedback on all actions

---

## Implementation Phases

### Phase 1: MVP (Minimum Viable Product)
- View current banners (read-only)
- Add new banner (form → commit)
- Basic GitHub integration
- Simple UI

### Phase 2: Core Features
- Edit existing banners
- Remove/archive banners
- Priority reordering
- Better error handling

### Phase 3: Enhanced Features
- Archive viewing/search
- Banner preview
- Bulk operations
- Change history/audit log

### Phase 4: Polish
- Improved UI/UX
- Mobile responsive
- Performance optimization
- Documentation

---

## Key Constraints

1. **No PR Process:** Must commit directly to `main` branch
2. **HTML Format:** Must maintain exact HTML structure and inline styles
3. **Tracking Comments:** Must preserve/update tracking comment format
4. **Archive First:** Must archive before removing banners
5. **Brand Separation:** US and Canada are separate files
6. **Deployment:** Changes must push to GitHub (Zendesk auto-deploys)

---

## Example User Flow

1. User opens webapp
2. Sees list of current US banners
3. Clicks "Add New Banner"
4. Fills form:
   - Brand: US
   - Type: Red Urgent
   - Priority: 1
   - Topic: "System Outage"
   - Text: "Known issue: System is currently down..."
   - Article: "https://supportcentral.libertytax.net/hc/en-us/articles/12345"
5. Clicks "Preview" → Sees banner preview
6. Clicks "Deploy" → Webapp commits and pushes to GitHub
7. User sees "Deployment successful" message
8. User can verify on help center in 2-5 minutes

---

## Reference Files

All documentation is in the repository:
- `README.md` - Full documentation
- `GITHUB_QUICK_EDIT_GUIDE.md` - Current manual workflow
- `.github/TEMPLATE_NEW_BANNER.md` - Banner templates
- `.github/TEMPLATE_ARCHIVE_ENTRY.md` - Archive format
- `ANNOUNCEMENT_WORKFLOW.md` - Detailed workflow (in main workspace)

---

## Success Criteria

The webapp is successful if:
- ✅ Non-technical users can add/edit/remove banners without training
- ✅ Complete workflow takes under 10 minutes
- ✅ All changes properly formatted and tracked
- ✅ Zero broken deployments
- ✅ Archive properly maintained
- ✅ Works reliably with GitHub API

---

## Questions to Consider

1. Should this be a single-page app or multi-page?
2. How to handle GitHub authentication securely?
3. Should we cache banner data or always fetch from GitHub?
4. How to handle concurrent edits?
5. Should we add a staging/preview environment?
6. Do we need user accounts or single shared access?

---

## Next Steps

1. Review this prompt and repository structure
2. Design the webapp architecture
3. Set up development environment
4. Implement Phase 1 MVP
5. Test with real GitHub repository
6. Iterate based on feedback

---

**Repository to work with:** https://github.com/escosuave/liberty-supportcentral-announcements.git

**Start by:** Reading the current files to understand the exact format, then design a simple UI that generates the correct HTML structure.

*Created: 2026-01-15*
