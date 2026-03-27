# 📚 StudyHub — Student Productivity App

Cross-device student productivity hub with login, cloud sync, Quizlet-style flashcards, and 3 visual themes — all in one HTML file.

---

## ✨ Features

| Feature | Details |
|---|---|
| 🔐 **Login / Register** | Email & password auth via Firebase |
| ☁️ **Cross-Device Sync** | All data saved to the cloud in real-time |
| 🌙 **Dark Mode** | Deep indigo — easy on the eyes at night |
| ☀️ **Light Mode** | Clean white workspace |
| 🍵 **Eye Protection** | Warm amber tones, reduced blue light |
| 🃏 **Flashcard Mode** | Flip cards, star, mark Know It / Still Learning |
| 🧠 **Learn Mode** | Auto-generated multiple-choice questions |
| ⚡ **Match Mode** | Timed tile-matching game |
| ✍️ **Write Mode** | Type answers to test recall |
| 📝 **Test Mode** | Full mixed test, graded with missed cards shown |
| ⚙️ **Settings** | Theme picker, preferences, account info |

---

## 🔥 Step 1 — Set Up Firebase (Free, ~5 min)

### 1.1 Create a Firebase Project
1. Go to **https://console.firebase.google.com**
2. Click **"Create a project"** → name it anything → Create
3. Disable Google Analytics (not needed) → Continue

### 1.2 Enable Email/Password Auth
1. Sidebar → **Build → Authentication → Get started**
2. Click **Email/Password** → Enable → Save

### 1.3 Create Firestore Database
1. Sidebar → **Build → Firestore Database → Create database**
2. Choose **"Start in test mode"** → Next → pick a region → Enable

### 1.4 Get Your Config
1. Click ⚙️ gear icon → **Project settings**
2. Scroll to **"Your apps"** → click **Web icon** `</>`
3. Give it a nickname → **Register app**
4. Copy the 6 values from the `firebaseConfig` object shown

---

## 📝 Step 2 — Add Config to the HTML

Open `index.html` in any text editor and find:

```javascript
const FIREBASE_CONFIG = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

Replace each `"YOUR_..."` with your actual Firebase values. Save the file.

---

## 🚀 Step 3 — Upload to GitHub & Go Live

1. Go to **github.com** → New repository → name it `studyhub` → Public → Create
2. Click **Add file → Upload files** → drag `index.html` → Commit
3. **Settings → Pages** → Branch: `main`, Folder: `/(root)` → Save
4. After ~60s your app is live at: `https://YOUR-USERNAME.github.io/studyhub/`

---

## 🔒 Step 4 — Secure Your Database

In Firebase Console → **Firestore → Rules**, replace with:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

Click **Publish**.

---

## 🎹 Keyboard Shortcuts

| Key | Action |
|---|---|
| `Space` | Flip flashcard |
| `→` / `↓` | Next card |
| `←` / `↑` | Previous card |
| `1` | Mark "Know It" |
| `2` | Mark "Still Learning" |
| `Alt + 1–8` | Switch pages |
| `Escape` | Close modals |

---

## ❓ Troubleshooting

- **Blank screen** → Check browser console (F12) for Firebase config errors
- **Login fails** → Confirm Email/Password auth is enabled in Firebase
- **Data not saving** → Confirm Firestore is created and in test mode
