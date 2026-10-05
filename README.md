# personal_website

Source for my academic website, served by GitHub Pages. Plain HTML and CSS,
no build step: what's in this folder is exactly what gets published.

## Layout

```
personal_website/
├── index.html     Home: photo, short intro, research interests, contact links
├── bio.html       Bio: longer bio, education, (optional) awards / teaching
├── research.html  Research: papers with arXiv / PDF / code links
├── style.css      shared look for all pages (colors, fonts, widths at the top)
├── images/        profile.jpg goes here (placeholder SVG shown until it exists)
├── files/         cv.pdf goes here
└── .nojekyll      tells GitHub Pages to serve the files as-is
```

Every spot that needs your input is marked with an `<!-- EDIT: ... -->` comment.
Run `grep -n "EDIT\|\[" *.html` to list them.

## Common edits

- **Photo:** copy your picture to `images/profile.jpg`. If you use a different name
  or format (e.g. `.png`), update the `<img src=...>` line in `index.html`.
- **CV:** copy it to `files/cv.pdf`.
- **New paper:** in `research.html`, copy the commented `TEMPLATE` block, paste it
  at the top of the list, and fill it in.
- **Navigation:** the header is repeated at the top of each page. If you add a page,
  add its link to all three headers.
- **"Last updated":** in each page's footer.

## Preview locally

```bash
cd ~/personal_website
python3 -m http.server 8000
```

Then open http://localhost:8000. (From the SCF, forward the port with
`ssh -L 8000:localhost:8000 <scf-host>`, or open the HTML files with VS Code's Live Preview.)

## Publish on GitHub Pages (first time)

1. On GitHub, create a **public** repository named exactly `<github-username>.github.io`
   (e.g. `aateyeh23.github.io`). Leave it empty: no README or license.
2. From this folder:
   ```bash
   git add -A
   git commit -m "Initial website"
   git remote add origin git@github.com:<github-username>/<github-username>.github.io.git
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages**, and under "Build and deployment" choose
   **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. The site is live at `https://<github-username>.github.io` within a minute or two.

After that, updating the site is just `git add -A && git commit -m "..." && git push`.
