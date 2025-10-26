# Phase 4 — Content Activation Prep
- [ ] Create first journal post (use post_template.md)
- [ ] Draft initial project case outline
- [ ] Add 404 page under /docs
- [ ] Plan tone & style review
- [ ] Optional:
    - [ ] **Blog taxonomy rendering** — confirm `custom_dir` recognition, or migrate to `mkdocs-blog-plugin` for tag/category support.
    - [ ] **Override testing** — introduce a test override file to verify template context.
    - [ ] **Documentation update** — capture lessons learned and share reproducible setup.

### Blog Integration Progress — October 26, 2025

**Objective:**  
Enable full Material for MkDocs blog functionality, including categories, tags, and per-post slugs.

**Status:**  
Partially complete — posts render correctly, including archives and slugs, but taxonomy pages (`/blog/categories/` and `/blog/tags/`) remain unresolved.

**Completed:**
- Material `blog` plugin active and verified.
- Post slugs, date parsing, and metadata rendering confirmed.
- Archive and index pages functional.
- YAML metadata validated and consistently parsed.

**Issues Outstanding:**
- `/blog/categories/` and `/blog/tags/` routes return 404.
- `{{ blog.tags }}` and `{{ blog.categories }}` variables remain undefined when rendered via Markdown (`mkdocs-macros-plugin` incompatibility).
- HTML overrides under `/overrides/blog/` not recognized by MkDocs (no `INFO - Using custom templates...` log line).
- Suspect issue: incorrect `custom_dir` resolution or plugin rendering order.

**Next Actions (future session):**
1. Confirm effective `custom_dir` discovery path with minimal test override (`main.html` marker).
2. Verify Material context injection for blog templates.
3. Explore fallback with `mkdocs-blog-plugin` for automatic taxonomy generation if native support remains partial.
4. Optionally isolate override testing in a minimal MkDocs sandbox.