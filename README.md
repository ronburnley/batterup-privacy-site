# BatterUp Privacy Site

A tiny static site that hosts the BatterUp privacy policy and support page.
Plain HTML and CSS, no build step, designed to be served from GitHub Pages.

## Files

- `index.html` — landing page with intro and links
- `privacy.html` — privacy policy (linked from App Store Connect)
- `support.html` — contact email and FAQ
- `style.css` — shared styles

## Before deploying

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

Live at the custom domain (migrated 2026-05-09):

```
https://batterupscorebook.com/
```

Specific pages:

- `https://batterupscorebook.com/privacy.html`
- `https://batterupscorebook.com/support.html`

The original `https://ronburnley.github.io/batterup-privacy-site/` URL
still works — GitHub Pages 301-redirects it to the apex.

### 5. Custom domain notes

- Apex DNS lives in Cloudflare as a CNAME at `@` flattening to
  `ronburnley.github.io`, plus a `www` CNAME doing the same. Cloudflare
  proxy is set to **DNS only** (gray cloud) — proxying through
  Cloudflare adds failure modes around Let's Encrypt renewal and gives
  this static site nothing useful.
- HTTPS cert is auto-provisioned and renewed by GitHub via Let's
  Encrypt. "Enforce HTTPS" is enabled in repo Settings → Pages.
- The `CNAME` file at repo root pins the custom domain so GitHub
  doesn't drop the binding on a redeploy.

### 6. Add the privacy policy URL to App Store Connect

1. Sign in to [App Store Connect](https://appstoreconnect.apple.com/)
2. Open the **BatterUp** app record
3. Go to **App Information** in the left sidebar
4. Scroll to **General Information** → **Privacy Policy URL**
5. Paste `https://batterupscorebook.com/privacy.html`
6. Click **Save**

The optional **Support URL** field (required when submitting for
review) takes `https://batterupscorebook.com/support.html`.

## Updates

Edit any HTML file, commit, and push to `main`. GitHub Pages redeploys
automatically.
