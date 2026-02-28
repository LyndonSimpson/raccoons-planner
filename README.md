# Raccoons Planner

Simple static site for GitHub Pages that shows one raccoon meme per day.

## Structure

```text
.
|-- index.html
|-- manifest.json
`-- raccoons/
    |-- 2026-03-01.jpg
    |-- 2026-03-02.jpg
    `-- 2026-03-03.png
```

## How it works

1. The page computes today's date in `YYYY-MM-DD`.
2. It loads `manifest.json`.
3. It looks up today's date in the manifest.
4. If a file is configured, it shows `raccoons/<filename>`.
5. If not, it shows `No raccoon scheduled today`.

## Monthly workflow

1. Add the new meme images to `raccoons/`.
2. Name each file with its display date, for example `2026-04-14.jpg`.
3. Add the matching entries to `manifest.json`.
4. Commit and push:

```bash
git add .
git commit -m "Add April raccoons"
git push
```

## GitHub Pages setup

1. Push this repo to GitHub.
2. In GitHub, open `Settings` > `Pages`.
3. Under `Build and deployment`, choose `Deploy from a branch`.
4. Select your branch, usually `main`, and folder `/ (root)`.
5. Save.
6. GitHub will publish the site at a URL like:

```text
https://<your-github-username>.github.io/<repo-name>/
```

## Notes

- Keep `manifest.json` valid JSON.
- Filenames in the manifest must match the actual files in `raccoons/`.
- GitHub Pages will not list files in a folder, which is why the manifest is required.
