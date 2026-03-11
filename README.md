# FMB QR Code Redirect

A lightweight GitHub Pages redirect page for use with a printed QR code.  
The QR code points to a **fixed GitHub Pages URL** — you can change where it ultimately sends visitors at any time, without reprinting the QR code.

---

## 🚀 One-Time Setup: Enable GitHub Pages

1. Push this repo to GitHub (see commands below).
2. Go to **Settings → Pages** in your GitHub repo.
3. Under **Source**, select **Deploy from a branch**.
4. Choose branch **`main`** and folder **`/ (root)`**, then click **Save**.
5. After ~60 seconds, your page will be live at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

> Use this URL when generating the QR code — it will never change.

---

## ✏️ How to Change the Destination URL

You only need to edit **one line** in `index.html`:

1. Open `index.html` on GitHub and click the **pencil ✏️ icon** (Edit).
2. Find this line (near the top, inside `<script>`):
   ```js
   var TARGET_URL = "https://example.com"; // ← EDIT THIS LINE
   ```
3. Replace `https://example.com` with your new destination URL.
4. Click **Commit changes** and wait ~30 seconds for GitHub Pages to rebuild.

That's it — no tools, no terminal needed.

> **Tip:** Also update the `<noscript>` meta refresh tag a few lines below to match the same URL (for users with JavaScript disabled).

---

## 🖥️ First-Time GitHub Push Commands

Run these commands from the project folder in Terminal:

```bash
# 1. Initialize git
git init
git add .
git commit -m "Initial: QR redirect page"

# 2. Create the repo on GitHub first at https://github.com/new
#    Suggested name: fmb-link

# 3. Connect and push
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main
```

---

## 🌐 Optional: Custom Domain

If you want a branded short URL (e.g. `go.yourbrand.com`) instead of the GitHub Pages URL:

1. Create a file named `CNAME` in this repo containing just your custom subdomain:
   ```
   go.yourbrand.com
   ```
2. In your DNS provider, add a **CNAME record**:
   - Host: `go`
   - Value: `<your-username>.github.io`
3. In GitHub **Settings → Pages**, enter the custom domain and enable **Enforce HTTPS**.

Allow up to 24 hours for DNS propagation.

---

## 📁 File Reference

| File | Purpose |
|------|---------|
| `index.html` | Redirect page — edit `TARGET_URL` to change destination |
| `CNAME` | Optional — add this file for a custom domain |
| `README.md` | This guide |
