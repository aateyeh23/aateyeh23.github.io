# personal_website

Source for my academic website, https://aateyeh23.github.io, served by GitHub Pages
from the `aateyeh23/aateyeh23.github.io` repository. Plain HTML and CSS,
no build step: what's in this folder is exactly what gets published.

## Layout

```
personal_website/
├── index.html     Home: photo, short intro, research interests, contact links
├── bio.html       Bio: longer bio, education, (optional) awards / teaching
├── research.html  Research: papers with arXiv / PDF / code links
├── cv.html        CV: web version of the CV
├── style.css      shared look for all pages (colors, fonts, widths at the top)
├── images/        profile photo (profile_placeholder.jpg)
├── files/         cv.pdf goes here (then uncomment the PDF link in cv.html)
├── cv_source/     LaTeX source of the CV; git-ignored, never published
└── .nojekyll      tells GitHub Pages to serve the files as-is
```


## Common edits

- **Photo:** replace `images/profile_placeholder.jpg`, or point the `<img src=...>`
  line in `index.html` at a new file.
- **CV:** update both `cv.html` and `cv_source/cv.tex`; put the compiled PDF in `files/cv.pdf`.
- **New paper:** in `research.html`, copy the commented `TEMPLATE` block, paste it
  at the top of the list, and fill it in.
- **Navigation:** the header is repeated at the top of each page. If you add a page,
  add its link to every header.
- **"Last updated":** in each page's footer.

## Preview locally

```bash
cd ~/personal/personal_website
python3 -m http.server 8000
```

Then open http://localhost:8000. (From the SCF, forward the port with
`ssh -L 8000:localhost:8000 <scf-host>`, or open the HTML files with VS Code's Live Preview.)

## Publish

```bash
git add -A && git commit -m "..." && git push
```

The live site updates about a minute after the push.
