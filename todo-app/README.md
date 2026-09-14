# Task Master — To-Do List Application

A beautiful, fully-featured to-do list application with **local storage persistence**. Create, manage, filter, and organize your tasks efficiently with a modern, responsive interface.

## ✨ Features

### Core Functionality
- ✅ **Add Tasks** — Quick input with Enter key support
- ✅ **Mark Complete** — Check off tasks as you finish them
- ✅ **Edit Tasks** — Modify title, description, and priority
- ✅ **Delete Tasks** — Remove tasks individually
- ✅ **Clear Completed** — Bulk delete all completed tasks
- ✅ **Local Storage** — All tasks persist across browser sessions

### Task Management
- 📝 **Task Titles & Descriptions** — Full task details
- 🎯 **Priority Levels** — Low, Medium, High priority tagging
- 📅 **Creation Dates** — Track when tasks were created
- 🏷️ **Status Tracking** — Active or Completed status

### Filtering & Organization
- 🔍 **Filter by Status** — All, Active, Completed
- 🔴 **Filter by Priority** — Show only high-priority tasks
- 📊 **Live Statistics** — Total, Completed, and Pending counts
- 📭 **Empty State** — Helpful message when no tasks match filter

### User Experience
- 🎨 **Modern Design** — Clean, professional interface
- 📱 **Fully Responsive** — Works on mobile, tablet, desktop
- 🌙 **Dark Mode Support** — Auto-detects system preference
- ⚡ **Smooth Animations** — Slide and fade transitions
- ♿ **Accessible** — ARIA labels, keyboard navigation

### Technical Features
- 🏪 **Local Storage API** — Zero server required
- 📦 **Single HTML File** — No dependencies or build step
- 🔒 **Data Persistence** — Tasks survive browser restart
- 🎯 **State Management** — Centralized app object
- 🛡️ **Input Validation** — XSS protection with HTML escaping

---

## 🚀 Quick Start

### Option 1: Open Directly in Browser
1. Download or clone the repo
2. Open `todo-app/index.html` in any modern browser
3. Start adding tasks!

### Option 2: Deploy to GitHub Pages
```bash
# Push to your GitHub repo
git add todo-app/index.html
git commit -m "Add Task Master to-do app"
git push origin main
```

Then access at:
```
https://username.github.io/repo-name/todo-app/
```

### Option 3: Deploy to Netlify
1. Connect your GitHub repo to Netlify
2. Build command: (leave empty)
3. Publish directory: `/`
4. Deploy!

Access at: `https://your-site.netlify.app/todo-app/`

---

## 📖 How to Use

### Adding a Task
1. Type your task in the input field
2. Press **Enter** or click the **Add** button
3. Task appears at the top of the list

### Completing a Task
- Click the **checkbox** next to any task to mark it complete
- Completed tasks show with strikethrough text
- Completed count in stats updates automatically

### Editing a Task
1. Click the **✏️ Edit** button on any task
2. Modify the title, description, or priority
3. Click **Save Changes**
4. Changes save to local storage instantly

### Deleting a Task
1. Click the **🗑️ Delete** button on any task
2. Confirm the deletion
3. Task is removed permanently

### Filtering Tasks
- **All** — Show all tasks
- **Active** — Show only incomplete tasks
- **Completed** — Show only finished tasks
- **High Priority** — Show only high-priority tasks

### Clearing Completed Tasks
- Click **Clear Completed Tasks** button at the bottom
- All finished tasks are removed at once
- Confirm the action when prompted

### Viewing Statistics
Real-time stats at the top show:
- **Total** — All tasks in the list
- **Completed** — Finished tasks
- **Pending** — Incomplete tasks

---

## 💾 Local Storage

### How It Works
All tasks are automatically saved to your browser's local storage. This means:
- ✅ Tasks persist across browser sessions
- ✅ No server required
- ✅ No login needed
- ✅ Completely private

### Storage Location
- **Chrome/Edge/Firefox/Safari**: Browser's local storage
- **Storage Key**: `tasks`
- **Storage Format**: JSON array
- **Storage Limit**: ~5-10MB per domain

### Clearing All Data
To reset your tasks:
1. Open browser DevTools (F12)
2. Go to **Console** tab
3. Run: `localStorage.clear()`
4. Refresh the page

Or manually:
1. DevTools → **Application** tab
2. Click **Local Storage**
3. Select your domain and delete `tasks` key

---

## 🎨 Customization

### Change Colors
Edit the CSS color variables at the top of the `<style>` tag:

```css
:root {
  --primary: #3B82F6;           /* Main blue */
  --primary-light: #60A5FA;     /* Hover blue */
  --primary-dark: #1E40AF;      /* Dark blue */
  --success: #10B981;           /* Checkmark green */
  --danger: #EF4444;            /* Delete red */
  --warning: #F59E0B;           /* Warning orange */
}
```

### Change Fonts
Replace font imports (line 10-11):
```html
<link href="https://fonts.googleapis.com/css2?family=YOUR+FONT:wght@400;500;600;700&display=swap" rel="stylesheet">
```

Then update CSS variables:
```css
--font-display: 'Your Font', sans-serif;
--font-body: 'Your Font', sans-serif;
```

### Add New Priority Levels
1. Update the `<select>` options in the edit form
2. Add new CSS classes like `.priority-urgent { ... }`
3. Update the priority rendering in the render function

### Change App Title
Edit line 262:
```html
<h1>✓ Task Master</h1>
<p>Your custom tagline here</p>
```

---

## 🔧 Advanced Features

### Export Tasks as JSON
Add this to the script section:
```javascript
function exportTasks() {
  const json = JSON.stringify(app.tasks, null, 2);
  const blob = new Blob([json], { type: 'application/json' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'tasks.json';
  a.click();
}
```

### Import Tasks from JSON
```javascript
function importTasks(file) {
  const reader = new FileReader();
  reader.onload = (e) => {
    try {
      app.tasks = JSON.parse(e.target.result);
      app.saveTasks();
      app.render();
    } catch (err) {
      alert('Invalid JSON file');
    }
  };
  reader.readAsText(file);
}
```

### Add Due Dates
Add a `dueDate` field to the task object:
```javascript
const task = {
  id: Date.now(),
  title: '',
  dueDate: '2026-12-31',  // Add this
  // ...
};
```

### Add Categories/Tags
```javascript
const task = {
  id: Date.now(),
  title: '',
  category: 'work',  // Add this
  tags: ['urgent', 'review'],  // Add this
  // ...
};
```

---

## 📱 Responsive Design

### Breakpoints
- **Desktop** (>600px) — Multi-column layout, full features
- **Mobile** (<600px) — Single column, touch-optimized buttons

### Mobile Features
- Full-screen optimized
- Large, touchable buttons
- Responsive grid adjusts automatically
- Horizontal scrolling for wide content

---

## ♿ Accessibility

### Built-in Features
- ✅ ARIA labels on all interactive elements
- ✅ Keyboard navigation (Tab, Enter, Esc)
- ✅ Color contrast meets WCAG AA standards
- ✅ Semantic HTML structure
- ✅ Focus indicators visible on all buttons
- ✅ Screen reader friendly

### Testing
1. **Keyboard Only** — Navigate using Tab key only
2. **Screen Reader** — Test with NVDA or JAWS
3. **Color Contrast** — Use WebAIM Color Contrast Checker
4. **Mobile** — Test on real devices

---

## 🐛 Troubleshooting

### Tasks Not Saving
**Problem**: Tasks disappear after refresh

**Solutions**:
1. Check if local storage is enabled in browser settings
2. Private/Incognito mode doesn't persist storage
3. Browser storage limit may be exceeded
4. Check DevTools: F12 → Application → Local Storage

### Tasks Not Loading
**Problem**: Page shows empty even though tasks were saved

**Solutions**:
1. Open DevTools (F12) → Console tab
2. Run: `console.log(JSON.parse(localStorage.getItem('tasks')))`
3. If empty, tasks may have been cleared
4. Clear cache and refresh (Ctrl+Shift+R)

### Checkbox Not Working
**Problem**: Can't mark tasks complete

**Solutions**:
1. Check browser console for JavaScript errors
2. Try refreshing the page
3. Clear browser cache
4. Try in a different browser

### Modal Won't Close
**Problem**: Edit dialog stays open

**Solutions**:
1. Press **Escape** key
2. Click **Cancel** button
3. Click outside the modal
4. Refresh the page

### Slow Performance
**Problem**: App is sluggish with many tasks

**Solutions**:
1. Clear completed tasks (reduces storage)
2. Export old tasks and create new list
3. Close other browser tabs
4. Check for browser extensions interfering

---

## 📊 Local Storage Details

### JSON Structure
```json
[
  {
    "id": 1726359726000,
    "title": "Buy groceries",
    "description": "Milk, eggs, bread",
    "priority": "high",
    "completed": false,
    "createdAt": "9/14/2026"
  },
  {
    "id": 1726359735000,
    "title": "Finish project",
    "description": "Complete the report",
    "priority": "medium",
    "completed": true,
    "createdAt": "9/13/2026"
  }
]
```

### View in DevTools
1. Open DevTools (F12)
2. Go to **Application** tab
3. Click **Local Storage**
4. Select your domain
5. Find key: `tasks`
6. View the JSON array

### Edit Manually
You can edit the JSON directly in DevTools:
1. Find the `tasks` key
2. Right-click → Edit value
3. Modify the JSON
4. Press Enter to save
5. Refresh page to see changes

---

## 🎯 Tips & Tricks

### Keyboard Shortcuts
- **Enter** — Add task from input field
- **Tab** — Navigate between elements
- **Click checkbox** — Toggle task completion
- **Click Edit** — Open edit modal
- **Escape** — Close modal
- **Click outside modal** — Close modal

### Priority Color Guide
- 🔴 **Red** — High priority (urgent)
- 🟡 **Yellow** — Medium priority (normal)
- 🔵 **Blue** — Low priority (optional)

### Best Practices
1. Use **High priority** only for urgent tasks
2. Add **descriptions** for complex tasks
3. Regularly **clear completed** tasks
4. Use **filters** to stay focused
5. Check **statistics** to track progress

---

## 🚀 Performance Tips

### Optimize Storage
- Clear completed tasks weekly
- Export old tasks (>6 months) as backup
- Keep list under 500 tasks for best performance

### Browser Support
| Browser | Support | Notes |
|---------|---------|-------|
| Chrome | ✅ Full | Latest version |
| Firefox | ✅ Full | Latest version |
| Safari | ✅ Full | iOS 14+ |
| Edge | ✅ Full | Latest version |
| IE 11 | ❌ None | Too old |

---

## 📝 License

Free to use and modify. No attribution required.

---

## 🔗 Related

- **Main Website**: `../index.html` (Brillers leather goods)
- **Deployment Guide**: `../DEPLOY.md`
- **Quick Start**: `../QUICKSTART.md`

---

## 💡 Future Ideas

- Add due dates and reminders
- Categories/tags for organization
- Dark mode toggle
- Export/import tasks
- Recurring tasks
- Task templates
- Collaborative lists
- Syncing across devices

---

**Happy task managing! 🎯✨**

Last updated: September 2026
