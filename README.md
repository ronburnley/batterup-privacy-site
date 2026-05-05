# BatterUp Privacy Site

A tiny static site that hosts the BatterUp privacy policy and support page.
Plain HTML and CSS, no build step, designed to be served from GitHub Pages.

## Files

- `index.html` — landing page with intro and links
- `privacy.html` — privacy policy (linked from App Store Connect)
- `support.html` — contact email and FAQ
- `style.css` — shared styles

## Before deploying

Swap these placeholder values in `privacy.html` and `support.html`:

- `support@example.com` — replace with the real support email (both files)
- Effective date in `privacy.html` if you want a different date than May 5, 2026

## Deploy to GitHub Pages

### 1. Create a new GitHub repo

On GitHub, create a new public repository, e.g. `batterup-privacy-site`.
Do not initialize it with a README, since this directory already has one.

### 2. Push these files to `main`

From this directory:

```sh
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/ronburnley/batterup-privacy-site.git
git push -u origin main
```

Replace `<username>` and `<reponame>` with your values.

### 3. Enable GitHub Pages

In the GitHub repo:

1. Go to **Settings** → **Pages**
2. Under **Build and deployment**, set:
   - **Source:** Deploy from a branch
   - **Branch:** `main`
   - **Folder:** `/ (root)`
3. Click **Save**

GitHub will publish the site within a minute or two. Refresh the Pages settings
page to see the live URL.

### 4. Site URL

The published URL will be:

```
https://ronburnley.github.io/batterup-privacy-site/
```

Specific pages:

- `https://ronburnley.github.io/batterup-privacy-site/privacy.html`
- `https://ronburnley.github.io/batterup-privacy-site/support.html`

### 5. Add the privacy policy URL to App Store Connect

1. Sign in to [App Store Connect](https://appstoreconnect.apple.com/)
2. Open the **BatterUp** app record
3. Go to **App Information** in the left sidebar
4. Scroll to **General Information** → **Privacy Policy URL**
5. Paste `https://ronburnley.github.io/batterup-privacy-site/privacy.html`
6. Click **Save**

You can use the same domain for the optional **Support URL** field
(`https://ronburnley.github.io/batterup-privacy-site/support.html`), which is required
when you submit a build for review.

## Updates

Edit any HTML file, commit, and push to `main`. GitHub Pages redeploys
automatically.
