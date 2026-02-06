# VALO LinkedIn Post Scheduler

A single-file web application for scheduling and managing LinkedIn thought leadership content. Built for VALO/ChrisMc with a focus on consistent, high-quality content creation.

![VALO Branding](https://img.shields.io/badge/VALO-Purple-8B5CF6)
![License](https://img.shields.io/badge/license-MIT-green)

## Features

### 📅 Monthly Calendar View
- Visual monthly calendar for scheduling posts
- Drag-and-drop rescheduling between dates
- Color-coded status indicators (Draft, Scheduled, Posted)
- Quick-add by clicking any date

### 📝 Post Composer
- **5 Content Templates:**
  - **Story** - Personal narratives with lessons
  - **List** - Structured, scannable content
  - **Hot Take** - Contrarian opinions that spark debate
  - **Question** - Engagement-driving questions
  - **Framework** - Methodologies and step-by-step guides

- **LinkedIn Preview** - See exactly how your post will look
- **Character Counter** - Stay within LinkedIn limits
- **One-click Hashtags** - Quick-add relevant tags

### 💡 Topic Suggestions
Curated ideas based on Chris's core themes:
- **AI Readiness** - Practical AI adoption frameworks
- **Value Proposition** - Articulating business value
- **Startup Culture** - Building high-performance teams
- **Entrepreneurship** - Founder lessons and insights

### 📊 Content Queue
- Sortable list view of all posts
- Filter by status and content type
- Quick actions: Edit, Copy, Delete
- Analytics: Breakdown by type and topic

### 📋 Clipboard Export
Since LinkedIn API requires OAuth app approval, posts can be:
- Copied to clipboard with one click
- Pasted directly into LinkedIn
- Formatted and ready to publish

### 💾 Data Persistence
- All data stored in browser LocalStorage
- No backend or account required
- Private - your content stays on your device

## Usage

### Getting Started

1. **Open the application:**
   ```bash
   # Simply open index.html in any modern browser
   open index.html
   ```

2. **Create your first post:**
   - Click "New Post" or go to the Composer tab
   - Select a template (Story, List, Hot Take, etc.)
   - Write your content
   - Set the scheduled date
   - Click "Save Post"

3. **Schedule posts:**
   - Switch to the Calendar tab
   - View your content schedule
   - Drag posts between dates to reschedule
   - Click any empty date to add a post

4. **Publish to LinkedIn:**
   - Open a post (click from Calendar or Queue)
   - Click "Copy for LinkedIn"
   - Paste into LinkedIn
   - Publish!

### Content Templates

#### Story
Personal narratives that connect emotionally with your audience.
```
I spent 6 months implementing AI tools.
Here's what actually worked...

[Your story]

Lesson learned: [Key takeaway]
```

#### List
Scannable, actionable content perfect for engagement.
```
5 signs your value proposition is confusing customers:

1. [Point]
2. [Point]
3. [Point]
4. [Point]
5. [Point]

Which resonated most?
```

#### Hot Take
Contrarian opinions that spark debate and visibility.
```
Unpopular opinion: [Bold statement]

Here's why I believe this...

[Your reasoning]

Agree or disagree? 👇
```

#### Question
Engagement-driving questions that invite responses.
```
What's your take on [topic]?

I've been thinking about this because...

[Context]

Curious to hear your thoughts!
```

#### Framework
Methodologies that position you as an expert.
```
I call this the [Name] Framework:

Step 1: [Action]
Step 2: [Action]
Step 3: [Action]

Here's how it works in practice...

[Example]
```

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + N` | New Post |
| `Ctrl/Cmd + S` | Save Post |
| `Esc` | Close Modal |

## Data Management

### Backup Your Content
Your posts are stored in browser LocalStorage. To backup:

1. Open browser DevTools (F12)
2. Go to Application → LocalStorage
3. Find `valo_linkedin_posts`
4. Copy the value and save to a file

### Restore From Backup
1. Open browser DevTools
2. Go to Application → LocalStorage
3. Set `valo_linkedin_posts` to your backup JSON

### Clear All Data
```javascript
// Run in browser console
localStorage.removeItem('valo_linkedin_posts');
location.reload();
```

## Technical Details

### Architecture
- **Single HTML File** - No build process required
- **Vanilla JavaScript** - No frameworks or dependencies
- **CSS Variables** - Consistent VALO theming
- **LocalStorage API** - Client-side data persistence

### Browser Compatibility
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### File Structure
```
valo-linkedin-scheduler/
├── index.html      # Complete application (all CSS/JS embedded)
└── README.md       # This file
```

## Customization

### Adding New Templates
Edit the `templates` object in the JavaScript:

```javascript
const templates = {
    yourtemplate: {
        name: 'Your Template',
        icon: '🔥',
        tips: 'Your tips here...',
        placeholder: 'Your placeholder...'
    }
};
```

### Adding Topic Suggestions
Edit the `topicSuggestions` array:

```javascript
const topicSuggestions = [
    {
        category: 'ai',
        categoryLabel: 'AI Readiness',
        title: 'Your Topic Title',
        description: 'Description here',
        template: 'story'
    }
];
```

### Changing Colors
Edit CSS variables at the top of the `<style>` section:

```css
:root {
    --valo-purple: #8B5CF6;
    --bg-dark: #0F0F0F;
    /* etc */
}
```

## Roadmap

### MVP (Complete)
- [x] Monthly calendar view
- [x] Content queue with drag-and-drop
- [x] Post composer with 5 templates
- [x] Topic suggestions
- [x] Status tracking (Draft → Scheduled → Posted)
- [x] Clipboard copy for manual posting
- [x] Local storage persistence
- [x] VALO dark theme branding

### Future Enhancements
- [ ] LinkedIn API integration (auto-posting)
- [ ] Analytics dashboard (engagement tracking)
- [ ] AI content suggestions
- [ ] Best time to post recommendations
- [ ] Content performance history
- [ ] Export to CSV/PDF
- [ ] Multi-account support

## Contributing

This is a personal tool for VALO/ChrisMc, but improvements are welcome:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License - feel free to use and modify for your own content scheduling needs.

## About VALO

VALO helps businesses articulate and deliver value. Built by Chris McMenemy for consistent thought leadership.

---

**Built with 💜 by the VALO team**
