# VALO LinkedIn Post Scheduler

A professional content calendar and automated posting system for LinkedIn, built for VALO Studios.

![VALO Scheduler](https://img.shields.io/badge/VALO-LinkedIn%20Scheduler-blue)
![Version](https://img.shields.io/badge/version-1.0.0-green)

## Features

### 📅 Content Calendar
- Monthly calendar view with visual post indicators
- Click any date to create a new post
- Color-coded status badges (Draft, Scheduled, Published, Failed)
- Quick navigation between months
- "Today" button for instant current month view

### ✍️ Post Composer
- Rich text editor with character counter (3000 char limit)
- Template library with 6 pre-built templates:
  - Thought Leadership
  - Company Update
  - Value Proposition
  - Engagement Question
  - Personal Story
  - Industry Trend
- One-click template insertion
- Date and time scheduling
- Auto-publish toggle

### 📋 Scheduled Posts Queue
- Timeline view of upcoming posts
- Filter by status (All, Scheduled, Drafts)
- Drag-and-drop ready architecture
- Quick actions: Edit, Preview, Delete, Publish Now
- Overdue post highlighting

### 📜 Post History/Archive
- Complete history of published and failed posts
- Search functionality
- Filter by status
- Duplicate posts for quick re-use
- Delete old posts

### 📝 Template Management
- 6 default professional templates
- Create custom templates
- Categorize templates (Thought Leadership, Company Update, etc.)
- One-click template usage

### 📤 Export Functionality
- **CSV Export**: Download all posts in spreadsheet format
- **JSON Export**: Full backup of posts and templates
- **JSON Import**: Restore from backup file

## Tech Stack

- **Frontend**: Pure HTML/CSS/JavaScript (single file)
- **Styling**: Tailwind CSS (via CDN)
- **Icons**: Lucide Icons
- **Storage**: LocalStorage (client-side persistence)
- **LinkedIn API**: Simulated (ready for API integration)

## Usage

### Creating a Post
1. Click "New Post" button or any date in the calendar
2. Choose a template (optional) or write from scratch
3. Set the date and time
4. Toggle "Auto-publish" for automatic posting
5. Click "Schedule" or "Save Draft"

### Using Templates
1. Navigate to Templates view
2. Click "Use Template" on any template card
3. Customize the content in the composer
4. Schedule as normal

### Managing the Queue
1. Switch to Queue view
2. Review upcoming posts in timeline format
3. Edit, delete, or publish posts immediately
4. Filter to see only scheduled or draft posts

### Exporting Data
1. Click the menu (three dots) in the header
2. Choose "Export CSV" for spreadsheet format
3. Choose "Export JSON" for full backup

## LinkedIn API Integration

The scheduler is architected for LinkedIn API integration. To connect:

1. Obtain LinkedIn API credentials from [LinkedIn Developer Portal](https://developer.linkedin.com/)
2. Add OAuth2 authentication flow
3. Replace `publishNow()` simulation with actual API call:

```javascript
// Example API integration
async function publishToLinkedIn(post) {
  const response = await fetch('https://api.linkedin.com/v2/posts', {
    method: 'POST',
    headers: {
      'Authorization': `Bearer ${accessToken}`,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      author: `urn:li:person:${personId}`,
      lifecycleState: 'PUBLISHED',
      specificContent: {
        'com.linkedin.ugc.ShareContent': {
          shareCommentary: { text: post.content },
          shareMediaCategory: 'NONE'
        }
      },
      visibility: { 'com.linkedin.ugc.MemberNetworkVisibility': 'PUBLIC' }
    })
  });
  return response.json();
}
```

## Branding

Consistent VALO Studios branding:
- Primary color: #3b82f6 (blue)
- Font: Inter
- Dark mode support
- Professional, clean UI

## Data Storage

All data is stored locally in the browser using LocalStorage:
- `valo_scheduler_posts`: All scheduled/draft/published posts
- `valo_scheduler_templates`: Custom templates
- `valo_scheduler_dark_mode`: UI preference

## Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13.1+
- Edge 80+

## Local Development

Simply open `index.html` in any modern web browser. No build step required.

```bash
# Optional: Serve with a local server
python3 -m http.server 8000
# or
npx serve .
```

## Deployment

### GitHub Pages
1. Push to GitHub repository
2. Enable GitHub Pages in repository settings
3. Select source branch (main)
4. Access at `https://yourusername.github.io/repo-name/`

### Static Hosting
Upload `index.html` to any static hosting service:
- Netlify
- Vercel
- Cloudflare Pages
- AWS S3

## Roadmap

- [ ] LinkedIn OAuth integration
- [ ] Media attachments (images, videos)
- [ ] Analytics dashboard (impressions, engagement)
- [ ] Team collaboration features
- [ ] Recurring post scheduling
- [ ] AI-powered content suggestions
- [ ] Best time to post recommendations

## License

Private - VALO Studios Internal Tool

## Credits

Built by Jarvis for VALO Studios
Part of the VALO Business Tools Suite
