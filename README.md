# The Cat's Space

A student jobsheet portal — Sasha and Badrul upload and track their mobile app dev jobsheets, lecturers review and check them off.

## Run locally

**Prerequisites:** Node.js

```
npm install
npm run dev
```

## Build

```
npm run build
```

## Uploading jobsheets to GitHub (PDF + live pages)

The Jobsheet page now saves uploads **straight into this repository**, and GitHub Pages publishes them.

```
public/uploads/
  sasha/
    manifest.json            <- remembers files, status, lecturer notes
    jobsheet-01/pdf/…        <- Upload PDF
    jobsheet-01/live/…       <- Upload Live (whole project, folders kept)
  badrul/
    manifest.json
    jobsheet-01/…
```

### One-time setup (per browser)
1. GitHub → Settings → Developer settings → **Fine-grained tokens** → *Generate new token*.
2. Repository access: **Only select repositories** → this repo.
3. Permissions → Repository → **Contents: Read and write**.
4. On the Jobsheet page click **Connect GitHub**, paste the token, press *Test & save*.

The token is stored only in that browser (localStorage). Never put it in the code or commit it.

### Using it
* **Upload PDF** – one PDF per jobsheet (or drag many into the bulk box).
* **Upload Live** – choose a folder, several files, or a `.zip` (HTML, CSS, JS, images, PDF, TXT… anything).
  The site keeps your folder structure, picks `index.html` as the entry page, checks every link
  (missing files, wrong upper/lower case, `C:\` paths) and auto-fixes `/root` paths before uploading.
* Each action is **one commit**. GitHub Pages then rebuilds (about 1–2 minutes); a badge shows
  *publishing → Live now*.
* Limits: 25 MB per file, 60 MB and 500 files per upload.
