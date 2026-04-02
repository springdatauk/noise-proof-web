# noise-proof-web

Public **GitHub Pages** site for **Noise Proof** (Spring Data Limited): support and privacy URLs for **App Store Connect** and **Apple Review**.

The parent **noiseProof** app repo lists `noise-proof-web/.git/` in **`.gitignore`** so you can keep this folder inside the app project without nested-repo noise when you use git at the app root.

- **Support:** `support.html` — `hello@springdata.uk` (no in-app support UI in Noise Proof).
- **Privacy:** `privacy-policy.html`

Live URLs (after you enable Pages, replace if you use a custom domain):

- `https://springdatauk.github.io/noise-proof-web/support.html`
- `https://springdatauk.github.io/noise-proof-web/privacy-policy.html`
- `https://springdatauk.github.io/noise-proof-web/` (index)

## Publish on GitHub (springdatauk)

### 1. Create the public repository

**GitHub web UI**

1. Sign in as an org member with permission to create repos under **springdatauk**.
2. **New repository** → Owner: **springdatauk** → Name: **`noise-proof-web`** → **Public** → Create (no README if you are pushing this folder).

**Or GitHub CLI** (from this directory, after `gh auth login`):

```bash
cd /path/to/noise-proof-web
git init
git add .nojekyll index.html privacy-policy.html support.html README.md
git commit -m "Add Noise Proof support and privacy pages for GitHub Pages"
gh repo create springdatauk/noise-proof-web --public --source=. --remote=origin --push
```

If the repo already exists empty:

```bash
git remote add origin https://github.com/springdatauk/noise-proof-web.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Open `https://github.com/springdatauk/noise-proof-web/settings/pages`.
2. Under **Build and deployment** → **Source**: **Deploy from a branch**.
3. **Branch:** `main` → **Folder:** `/ (root)` → **Save**.
4. Wait a minute or two; the site will be at `https://springdatauk.github.io/noise-proof-web/`.

### 3. App Store Connect

- **Privacy Policy URL:** `https://springdatauk.github.io/noise-proof-web/privacy-policy.html`
- **Support URL:** `https://springdatauk.github.io/noise-proof-web/support.html`

The iOS app’s purchase flow links to the privacy policy URL in code (`AppConfiguration.legalPrivacyPolicyURL`). Update the app if you change hosting.

## Contents

| File | Purpose |
|------|---------|
| `index.html` | Short landing with links (optional for reviewers). |
| `support.html` | Support contact for Apple Review; **not** linked inside the app. |
| `privacy-policy.html` | Privacy policy for the App Store and in-app legal link. |

No connection to any other marketing site—this repo is only these static pages.
