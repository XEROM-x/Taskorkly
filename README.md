# Taskorkly

Static site for **taskorkly.com** — a comparison site for products, software, and AI tools, plus a landing page for the upcoming Google Play app.

## Structure

```
taskorkly/
├── index.html          Home
├── comparisons.html     Comparison categories + entries
├── app.html              Google Play app landing page
├── about.html            Mission + methodology
├── contact.html          Contact form + info
├── css/
│   └── style.css
├── js/
│   └── script.js
├── assets/                (put images here)
└── CNAME                  Custom domain for GitHub Pages
```

No build step — plain HTML/CSS/JS. Open `index.html` directly in a browser to preview locally, or use a simple local server:

```bash
python3 -m http.server 8000
```

## Deploying to GitHub Pages

1. Create a new GitHub repo (e.g. `taskorkly`) and push everything in this folder to the `main` branch.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Save. GitHub will publish at `https://<your-username>.github.io/taskorkly/`.

## Connecting taskorkly.com

The `CNAME` file already contains `taskorkly.com`, which is what tells GitHub Pages to serve the site on your custom domain instead of the github.io URL.

1. At your domain registrar (wherever you bought taskorkly.com), add these DNS records:
   - Four **A** records for `@` pointing to GitHub Pages' IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A **CNAME** record for `www` pointing to `<your-username>.github.io`
2. Back in **Settings → Pages** on GitHub, enter `taskorkly.com` as the Custom domain and save (this also verifies the CNAME file is in place).
3. Once DNS propagates (can take a few hours), tick **Enforce HTTPS**.

## To edit later

- Colors, fonts, spacing all live in `css/style.css` under the `:root` block at the top — change a value there and it updates the whole site.
- Each comparison on `comparisons.html` is one `.compare-row` block — copy/paste one and edit the text to add a new entry.
- Add real screenshots by dropping images into `assets/` and swapping out the CSS-drawn phone mockup in `app.html`.
