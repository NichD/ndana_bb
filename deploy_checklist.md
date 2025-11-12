# 🚀 Deploy Checklist — ndana-builder-hub

**Purpose:**  
To document environment settings, build configuration, and post-deployment verification steps for the BrandBuilder / Builder Hub site.  
_Last updated: 2025-11-11_

---

## 1. 🧱 Pre-Deployment

- [ ] Confirm **Python 3.12** virtual environment is active:
  ```bash
  source .venv/bin/activate
  ```
- [ ] Verify dependencies installed and current:
  ```bash
  pip install -r requirements.txt
  ```
- [ ] Run local build and check for warnings:
  ```bash
  mkdocs build
  ```
- [ ] Preview locally to confirm correct rendering:
  ```bash
  mkdocs serve
  ```
- [ ] Validate `netlify.toml` syntax (redirects, environment, Python version).
- [ ] Confirm blog post frontmatter and metadata render correctly.
- [ ] Verify `extra.css` changes apply across light/dark modes.

---

## 2. 🔧 Git & Version Control

- [ ] Check status and ensure working directory is clean:
  ```bash
  git status
  ```
- [ ] Commit changes with descriptive message:
  ```bash
  git add .
  git commit -m "vX.Y.Z – Deployment summary"
  ```
- [ ] Tag release for version tracking:
  ```bash
  git tag -a vX.Y.Z -m "Phase X.Y.Z – Release notes"
  ```
- [ ] Push to main and publish tag:
  ```bash
  git push origin main
  git push origin vX.Y.Z
  ```

---

## 3. 🌐 Netlify Build

- [ ] Confirm Netlify build triggers automatically from push.
- [ ] Monitor **Netlify → Deploys → Build Logs** for errors or warnings.
- [ ] Check redirect behavior and DNS resolution:
  - ✅ `https://builder.npdana.pro`
  - ✅ `https://npdana.pro` (redirect)
- [ ] Validate SSL certificate is active and valid.
- [ ] Ensure `_redirects` or `netlify.toml` routes apply correctly.

---

## 4. 🔍 Post-Deployment Verification

- [ ] Hard refresh browser (Cmd + Shift + R) to bypass cache.
- [ ] Check all navigation links and sidebar entries.
- [ ] Confirm hero image, accent colors, and CSS overrides render correctly.
- [ ] Test blog index, post slugs, and category listings.
- [ ] Verify that excluded files (internal, phase docs) are not publicly accessible.
- [ ] Confirm build timestamp and commit hash in footer (if enabled).

---

## 5. 🧾 Post-Build Documentation

- [ ] Update `phase_reviews.md` with deployment confirmation and version number.
- [ ] If structure changed, regenerate:
  ```bash
  tree -L 3 -I '.venv|__pycache__|site' > directory_structure.md
  ```
- [ ] Add any technical notes or learnings to `internal/implementation_notes.md`.
- [ ] Optional: Invalidate CDN cache via Netlify if changes don’t appear.

---

✅ **Deployment complete** when all checks above are marked.