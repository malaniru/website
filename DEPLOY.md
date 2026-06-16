# Deploy Guide — Marketing Site to GitHub Pages

Two parts: (1) commit this folder to a new empty GitHub repository, then (2) turn that repository into a live website with GitHub Pages.

You need [git installed](https://git-scm.com/downloads) and a free GitHub account. Run the commands from a terminal **inside this folder** (`20260616-marketing-site-github-package`).

---

## Part 1 — Commit to a new, empty GitHub repository

### Step 1. Create the empty repo on GitHub

1. Go to https://github.com/new
2. **Repository name:** pick one, e.g. `malaniru-site`
3. **Visibility:** Public (required for free GitHub Pages; private Pages needs a paid plan)
4. **Do NOT** check "Add a README", "Add .gitignore", or "Choose a license". The repo must be empty so your push isn't rejected.
5. Click **Create repository**.

GitHub then shows a quick-setup page with your repo URL. Copy the HTTPS URL — it looks like:

```
https://github.com/YOUR-USERNAME/malaniru-site.git
```

### Step 2. Initialize git in this folder and commit

Open a terminal, `cd` into this folder, then run:

```bash
git init
git add .
git commit -m "Initial commit: Malaniru marketing site"
git branch -M main
```

What each line does: start tracking the folder, stage every file, save the first commit, and name the branch `main`.

### Step 3. Connect to your GitHub repo and push

Replace the URL with the one you copied in Step 1:

```bash
git remote add origin https://github.com/YOUR-USERNAME/malaniru-site.git
git push -u origin main
```

If prompted to authenticate, sign in to GitHub. When using HTTPS, GitHub asks for a **Personal Access Token** instead of your password — create one at https://github.com/settings/tokens (classic token with the `repo` scope) and paste it as the password.

Refresh your repo page on GitHub; all the files should now appear.

> **Re-deploying later:** after editing files, run `git add . && git commit -m "your message" && git push`. Pages rebuilds automatically.

---

## Part 2 — Turn the repo into a GitHub Pages site

### Step 1. Enable Pages

1. On your repository, click **Settings** (top tab).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, select **`main`** and the folder **`/ (root)`**.
5. Click **Save**.

Because `index.html` sits at the root of the repo, GitHub Pages serves it as the homepage automatically.

### Step 2. Wait, then visit your site

The first build takes ~1–2 minutes. When it's ready, the Pages settings screen shows a green banner with your live URL:

```
https://YOUR-USERNAME.github.io/malaniru-site/
```

Open it. You should land on the homepage (`index.html`), and the navigation links between pages should all work.

### Optional but recommended — add a `.nojekyll` file

By default GitHub Pages runs your files through Jekyll, which ignores any file or folder whose name starts with an underscore. This site has none, so it'll work either way — but adding an empty `.nojekyll` file guarantees every file is served exactly as-is and slightly speeds up builds:

```bash
touch .nojekyll
git add .nojekyll
git commit -m "Add .nojekyll to disable Jekyll processing"
git push
```

### Optional — custom domain (e.g. malaniru.com)

In **Settings → Pages → Custom domain**, enter your domain and save, then add the DNS records GitHub specifies at your domain registrar (an `A`/`ALIAS` record for an apex domain, or a `CNAME` record pointing to `YOUR-USERNAME.github.io` for a subdomain). Enable **Enforce HTTPS** once the certificate is issued.

---

## Quick reference

```bash
# one-time setup
git init
git add .
git commit -m "Initial commit: Malaniru marketing site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/malaniru-site.git
git push -u origin main

# then: Settings -> Pages -> Source: Deploy from a branch -> main / (root) -> Save
# live at: https://YOUR-USERNAME.github.io/malaniru-site/

# future updates
git add .
git commit -m "Describe your change"
git push
```
