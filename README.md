# Shamaryah Udeakpu — Portfolio Website

A futuristic, interactive portfolio with a **private admin dashboard** you can use to post
new projects, awards, and achievements — no coding needed.

Files:
- `index.html` — the whole website (HTML + CSS + JavaScript in one file)
- `data.json` — your published content (projects, awards, achievements)
- `README.md` — this guide

---

## 1. Put it online with GitHub Pages (free)

1. Create a free account at <https://github.com> if you don't have one.
2. Click **New repository**. Name it `portfolio` (or, for a clean URL, name it
   `your-username.github.io`). Set it to **Public**. Click **Create**.
3. Click **Add file → Upload files**, and drag in `index.html` and `data.json`
   (and this `README.md`). Click **Commit changes**.
4. Go to the repo's **Settings → Pages**.
5. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**,
   **Folder: /(root)**, then **Save**.
6. Wait ~1 minute. Your site is live at:
   - `https://your-username.github.io/portfolio/`  (if you named it `portfolio`), or
   - `https://your-username.github.io/`  (if you named the repo `your-username.github.io`).

That link is what you share with companies and on your CV/LinkedIn.

---

## 2. Log in to your admin dashboard

1. Go to your live site and add **`#admin`** to the end of the URL, e.g.
   `https://your-username.github.io/portfolio/#admin`
   (There's also a small 🔒 lock icon at the bottom-right of the site, and an
   "admin" link in the footer.)
2. Enter your passcode. The default is **`shamzy2026`** — **change it** (see section 4).
3. You'll see the **Control Panel** with three tabs: **Projects, Awards, Achievements**.

In each tab you can **add**, **edit**, and **delete** items using the form on the left.
Your changes are saved instantly in your browser as you work.

---

## 3. Publish your changes so visitors can see them

GitHub Pages is a *static* host, so your edits live in your browser until you publish them.
To make new posts visible to everyone:

1. In the dashboard, make your edits (add a project, award, etc.).
2. Click **⬇ Publish (export data.json)**. This downloads an updated `data.json`.
3. Go to your GitHub repo → click the existing `data.json` → the pencil ✏️ (or
   **Add file → Upload files**) → replace it with the new one → **Commit changes**.
4. Refresh your live site — the new content is now visible to all visitors, on any device.

Helpful buttons in the dashboard:
- **⬆ Import data.json** — load a `data.json` file back in (e.g. to edit on another computer).
- **⟳ Load published** — pull the live `data.json` from your site into the editor.
- **↺ Reset to default** — restore the original starting content.

> Tip: bookmark the dashboard URL on your phone so you can draft posts anywhere, then
> publish from a computer when convenient.

---

## 4. Change your passcode (do this before sharing the site)

1. Open `index.html` in any text editor.
2. Find this line (near the start of the `<script>` section):
   ```js
   const ADMIN_PASS='shamzy2026';   // ← CHANGE THIS to your own passcode
   ```
3. Replace `shamzy2026` with your own passcode. Save and re-upload `index.html` to GitHub.

**Note on security:** this is a lightweight gate, fine for a personal portfolio — it keeps
casual visitors out of the dashboard, but a determined person could read the passcode in the
page source. For real login security, use the Firebase upgrade below.

---

## 5. Adding images / photos of your robots

In the project form there's an **Image URL** field. The easiest options:
- **Commit images to your repo:** make an `images/` folder in the repo, upload a photo, then
  use the path `images/robot-dog.jpg` as the Image URL.
- **Google Drive / Google Cloud / Imgur:** upload there and paste a *direct image link*.

If you leave the Image URL blank, the site automatically shows a clean built-in schematic
icon for that project — so it always looks complete.

---

## 6. Optional upgrade: post from anywhere, instantly (Firebase)

If you'd rather post from any device and have it go live immediately — with no `data.json`
export/commit step and with real password login — connect the site to **Firebase** (free tier):

1. Create a project at <https://firebase.google.com> → add **Firestore Database** and
   **Authentication** (Email/Password).
2. Store your projects/awards/achievements as Firestore documents.
3. Replace the `loadData()` and `saveLocal()` functions in `index.html` with Firestore
   reads/writes, and replace the passcode check with Firebase Auth sign-in.
4. For image uploads, add **Firebase Storage**.

This keeps everything else (the design, the dashboard layout) exactly the same — only the
"where data is stored" part changes. Tell me if you want me to wire this up for you.

---

Built with care. Questions or tweaks — just ask.
