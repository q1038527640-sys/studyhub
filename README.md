# 📚 StudyHub — Student Productivity App

A complete, offline-first student productivity dashboard built in a single HTML file.  
No frameworks to install. No internet required. Just open and use.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📊 **Dashboard** | Overview of tasks, events, and subject progress |
| 📅 **Calendar** | Monthly calendar with colour-coded events |
| ✅ **Task Manager** | Add tasks with priority, subject, due date, and notes |
| 📓 **Notes** | Subject-organised note-taking with search |
| 🃏 **Flashcards** | Study cards with flip animation and shuffle |
| ⏱️ **Pomodoro Timer** | Customisable focus timer with session logging |
| 🎓 **Subjects** | Manage subjects with colour tags and progress tracking |

**All data is saved automatically in your browser's localStorage — no account or server needed.**

---

## 🚀 How to Upload to GitHub (Step-by-Step)

### Step 1 — Create a GitHub Account
1. Go to [https://github.com](https://github.com)
2. Click **Sign up** and follow the instructions
3. Verify your email address

---

### Step 2 — Create a New Repository
1. Once logged in, click the **+** icon (top-right) → **New repository**
2. Fill in:
   - **Repository name**: `studyhub` (or any name you like)
   - **Description**: `My student productivity dashboard`
   - Set it to **Public** (so GitHub Pages can host it for free)
   - Check **Add a README file**
3. Click **Create repository**

---

### Step 3 — Upload the File
1. Inside your new repository, click **Add file** → **Upload files**
2. Drag and drop the `index.html` file onto the upload area (or click to browse)
3. Scroll down and click **Commit changes**

Your file is now on GitHub!

---

### Step 4 — Enable GitHub Pages (Free Hosting!)
This makes your app accessible from any browser via a link.

1. In your repository, click **Settings** (top menu)
2. Scroll down and click **Pages** (left sidebar)
3. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click **Save**
5. Wait 60 seconds, then refresh the page
6. You will see: **"Your site is live at https://YOUR-USERNAME.github.io/studyhub/"**

Your app is now live on the internet!

---

### Step 5 — Access Your App
- **Local**: Double-click `index.html` on your computer to open it in any browser
- **Online**: Visit `https://YOUR-USERNAME.github.io/studyhub/`
- Bookmark it on your phone or desktop for quick access

---

## How to Update the App Later

### Option A — Upload via Browser (Easy)
1. Go to your GitHub repository
2. Click on `index.html`
3. Click the pencil icon (Edit)
4. Delete all old content and paste in the new code
5. Click **Commit changes**

### Option B — GitHub Desktop (Recommended for regular use)
1. Download [GitHub Desktop](https://desktop.github.com/)
2. Sign in with your GitHub account
3. Click **Clone a repository** and select your `studyhub` repo
4. Replace the `index.html` file on your computer
5. In GitHub Desktop, write a commit message and click **Commit to main** then **Push origin**

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Alt + 1` | Dashboard |
| `Alt + 2` | Calendar |
| `Alt + 3` | Tasks |
| `Alt + 4` | Notes |
| `Alt + 5` | Flashcards |
| `Alt + 6` | Timer |
| `Alt + 7` | Subjects |
| `Escape` | Close modal |

---

## Tips for Getting Started

1. **Start with Subjects** — Add your subjects first so you can tag tasks, notes, and events
2. **Double-click** a calendar event to edit it
3. **Click a flashcard** to flip between question and answer
4. Allow **browser notifications** for Pomodoro timer alerts
5. Your data saves automatically — clearing browser data will erase it

---

## Privacy

All data is stored **only in your browser** using `localStorage`. Nothing is sent to any server.

To back up your data, open the browser console (`F12` → Console) and type:
```js
JSON.stringify(localStorage)
```
Copy and save the output somewhere safe.

---

## File Structure

```
studyhub/
└── index.html    (the entire app)
```

Everything is in one file for maximum simplicity.
