# Marlo — Portfolio Site

A simple, dependency-free portfolio site: plain HTML/CSS/JS, no build step.
This `package.json` only adds a local preview server and nothing else —
the site itself needs no framework, bundler, or compilation.

This file (`README.md`) is just documentation for you and anyone browsing
the repo on GitHub — it has no effect on the live site. The site that
gets deployed is `index.html` and the other `.html` files.

## Structure

```
index.html              Home page (bio + photo)
audio-production.html   Audio Production Samples
sound-design.html       Sound Design Work
audio-software.html     Audio Software Engineering Projects
pure-data.html          Pure Data Patches
assets/style.css        All styling (colors, fonts, layout)
assets/script.js        Mobile nav toggle + active-link highlight
package.json            Local dev server script (not needed for deployment)
```

## Running it locally

You need [Node.js](https://nodejs.org) installed (any recent LTS version).
From a terminal (Git Bash on Windows works fine) in this folder:

```bash
npm install
npm run dev
```

Then open the URL it prints (something like `http://localhost:3000`) in
your browser. Edit any `.html` or `.css` file, save, and refresh the
browser to see the change — there's no build step to wait on.

## Tracking changes with git

If this folder isn't already a git repo:

```bash
git init
git add .
git commit -m "Initial commit"
```

From then on, whenever you make changes you want saved:

```bash
git add .
git commit -m "Describe what changed"
git push
```

## Editing your bio and photo

Open `index.html` and edit the paragraphs inside `<div class="bio-text">`.
To add your photo, follow the comment directly above the `<div class="bio-panel">`
block — put an image at `assets/images/profile.jpg` and swap the
placeholder `<div class="photo-placeholder">...</div>` for
`<img src="assets/images/profile.jpg" alt="Marlo" />`.

## Adding a new project to any section

Each work page (`audio-production.html`, `sound-design.html`,
`audio-software.html`, `pure-data.html`) has one **example card** wrapped
in HTML comments that say:

```html
<!-- EXAMPLE PROJECT CARD — copy this whole <div class="card"> block ... -->
<div class="card">
  ...
</div>
<!-- ========================= END EXAMPLE CARD ========================= -->
```

To add a new project:

1. Open the relevant page in any text editor.
2. Copy an existing `.card` block (the example, or any project you've
   already added).
3. Paste it directly above the `<div class="card placeholder">` block
   (the "more coming soon" card) so new work appears before it.
4. Edit the title, date/meta line, description, tags, and links.
5. Delete the `<audio>` or `<div class="embed">` block if you don't need
   it — they're optional.
6. Save, then `git add`, `git commit`, `git push` to publish the change.

## Changing colors/fonts

Everything themeable lives at the top of `assets/style.css` in the
`:root { ... }` block — change `--terracotta`, `--teal`, `--plum`,
`--rose`, `--bg`, etc. and the whole site updates.

## Deploying

This site is deployed on Vercel, connected to this repo's GitHub remote.
Every push to the `main` branch redeploys automatically — see the setup
instructions provided alongside this project for connecting a fresh
repo to Vercel.
