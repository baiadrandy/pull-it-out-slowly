# Pull It Out Slowly

Guild website for **Pull It Out Slowly**, built as a static site (plain HTML/CSS/JS, no build step required).

- Live copy: `index.html`
- Styles: `style.css`
- Logo / favicons: `assets/`
- Discord: https://discord.gg/fZzsrhgz

## Preview locally

No build tools needed. Either:

- Open `index.html` directly in a browser, or
- Run a quick local server from this folder:
  ```
  python3 -m http.server 8000
  ```
  then visit `http://localhost:8000`

## Editing content

All copy lives in `index.html` — guild description, "How we play" cards, and stats
in the About section are placeholders based on what's public so far. Edit freely;
no other files need to change for text edits.

Colors and fonts are defined as CSS variables at the top of `style.css` under `:root`
if you want to adjust the palette later.

## Deploying with GitHub Pages

1. Push this repo to GitHub (see commands below).
2. On GitHub: **Settings → Pages** → set **Source** to the `main` branch, root folder.
3. GitHub Pages will pick up the `CNAME` file automatically and serve the site at
   `pullitoutslowly.com` once DNS (below) is set.

```bash
git remote add origin https://github.com/<your-username>/pull-it-out-slowly.git
git branch -M main
git push -u origin main
```

## Pointing the GoDaddy domain at GitHub Pages

In GoDaddy, go to **Domain Settings → DNS → Manage DNS** for `pullitoutslowly.com` and set:

**A records** (for the apex domain `pullitoutslowly.com`) — add all four, pointing to GitHub Pages' IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME record** (for `www.pullitoutslowly.com`):
```
www  →  <your-username>.github.io
```

DNS changes can take anywhere from a few minutes to a few hours to propagate.
Once it resolves, enable **Enforce HTTPS** in the repo's Pages settings for a free
GitHub-managed SSL certificate.
