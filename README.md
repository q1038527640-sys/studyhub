# 📚 StudyHub

A single-file academic productivity app — Calendar, Tasks, Notes, Flashcards, and Pomodoro Timer — backed by Firebase Auth + Firestore.

---

## 🚀 Quick Start

### 1. Create a Firebase Project
1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → give it a name → continue
3. Click **Add app** (the `</>` web icon) → register your app
4. Copy the config object shown — you'll need it in Step 3

### 2. Enable Firebase Services
| Service | Steps |
|---|---|
| **Authentication** | Firebase Console → Authentication → Sign-in method → Email/Password → Enable |
| **Firestore** | Firebase Console → Firestore Database → Create database → choose region → Start in **production mode** |

### 3. Paste Your Firebase Config into `index.html`
Open `index.html` and find the `FIREBASE_CONFIG` block (search for `PASTE_YOUR_API_KEY_HERE`).
Replace each `PASTE_YOUR_*_HERE` value with the real values from your Firebase project:

```js
const FIREBASE_CONFIG = {
  apiKey:            "AIzaSy...",
  authDomain:        "myproject.firebaseapp.com",
  projectId:         "myproject",
  storageBucket:     "myproject.appspot.com",
  messagingSenderId: "123456789",
  appId:             "1:123:web:abc"
};
```

### 4. Deploy Firestore Security Rules
**This step is critical — without it, any logged-in user can read everyone's data.**

**Option A — Firebase Console (easiest):**
1. Firebase Console → Firestore Database → **Rules** tab
2. Delete all existing content
3. Paste the contents of `firestore.rules`
4. Click **Publish**

**Option B — Firebase CLI:**
```bash
npm install -g firebase-tools
firebase login
firebase init firestore   # select your project, accept firestore.rules as the rules file
firebase deploy --only firestore:rules
```

### 5. Deploy the App
**Firebase Hosting (recommended — free):**
```bash
firebase init hosting     # set public directory to "." (current folder), single-page app: No
firebase deploy --only hosting
```

Or just drag `index.html` into any static host (Netlify, Vercel, GitHub Pages).

---

## 🔒 Security Checklist

- [ ] Firebase config values are **not** the `PASTE_YOUR_*` placeholders
- [ ] Firestore security rules have been published (see `firestore.rules`)
- [ ] Firebase API key is restricted in [Google Cloud Console](https://console.cloud.google.com) → APIs & Services → Credentials → your key → **HTTP referrers** → add your domain
- [ ] Your repo is **private** OR `index.html` is listed in `.gitignore` (if it contains hardcoded keys)

---

## 📦 Data & Storage Notes

- All user data is stored in a **single Firestore document** per user at `users/{uid}`
- Firestore has a **1 MB per document limit**
- StudyHub warns you at **800 KB** and blocks saves at **950 KB** (visible in Settings → Storage Used)
- If you approach the limit, delete old flashcard sets, notes, or past events
- Future improvement: migrate `fcSets` to a Firestore subcollection to scale beyond 1 MB

---

## 🛠️ Local Development

No build step needed. Just open `index.html` in a browser — but Firebase Auth requires a real domain (not `file://`).

Use a local server:
```bash
# Python
python3 -m http.server 3000

# Node
npx serve .
```

Then open [http://localhost:3000](http://localhost:3000).

---

## 🗂️ File Structure

```
index.html          ← The entire app (HTML + CSS + JS)
firestore.rules     ← Firestore security rules (deploy to Firebase)
.gitignore          ← Prevents accidentally committing secrets
README.md           ← This file
```
