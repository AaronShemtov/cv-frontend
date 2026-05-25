# cv-frontend

Aaron Shemtov's CV — deployed at [cv.1ms.my](https://cv.1ms.my).

Static one-page CV with collapsible experience blocks, dark/light theme, and PDF downloads.

## Editing content

All content lives in `public/index.html`. To update:

- **Add a job**: copy any existing `<article class="experience expanded">` block and edit the title, dates, and bullets.
- **Update CV PDF**: replace `public/cv.pdf` with a new file (same filename).
- **Update Cover Letter**: replace `public/cover-letter.pdf`.
- **Add skills**: edit `<div class="skills">` — each skill group is a `<div class="skill-group">` with an `<h3>` and a `<p>`.

After editing, push to `main`. GitHub Actions builds an arm64 image, pushes to OCIR with semver tag `0.0.<run_number>`. Flux Image Automation in the OKE cluster detects the new tag and rolls out the updated deployment within ~2 minutes.

## Stack

- Static HTML/CSS/JS — no build step, no framework
- nginx-unprivileged (Alpine) container, ~20 MB
- GitHub Actions CI → OCIR
- Flux Image Automation closes the GitOps loop

## Local preview

```bash
cd public
python3 -m http.server 8000
# open http://localhost:8000
```

## License

MIT — see `LICENSE`.
