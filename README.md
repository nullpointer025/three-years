# Three Years

A single-page anniversary site. Static HTML/CSS/JS, no build step.

## Structure

- `index.html` — the page
- `assets/photos/` — drop gallery images here
- `CNAME` — custom domain for GitHub Pages (set to `makeitcozzify.com`)

## Personalize before publishing

Open `index.html` and edit:

- `— always, [your name]` (message section) — your sign-off
- The three timeline cards ("How it started", "A memory worth keeping", "Right now") — replace the placeholder paragraphs
- Gallery photos — save images into `assets/photos/`, then set each `<img src="">` in the `.gallery` block to the matching path, e.g. `src="assets/photos/photo-1.jpg"`. Leave `src=""` for any card you want to keep as a placeholder.

## Deploy to GitHub Pages

1. Create a new GitHub repo (public, or private if you're on a paid plan — Pages with a custom domain works either way).
2. Push this project:
   ```
   git remote add origin https://github.com/<you>/three-years.git
   git branch -M main
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**. Under "Build and deployment", set Source to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Under **Custom domain**, enter `makeitcozzify.com` and save (this writes/confirms the `CNAME` file). Wait for DNS check to pass, then enable **Enforce HTTPS**.

## DNS setup (at your domain registrar)

Since `makeitcozzify.com` is an apex/root domain, point it at GitHub Pages with four **A** records:

| Type | Host | Value          |
|------|------|----------------|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

Optional, if you also want `www.makeitcozzify.com` to work:

| Type  | Host | Value                  |
|-------|------|------------------------|
| CNAME | www  | `<you>.github.io`      |

DNS propagation can take anywhere from a few minutes to a few hours.
