# Templates Directory — BrandBuilder

This folder contains reusable Markdown templates for structured content creation within the `ndana_bb` BrandBuilder repository.

---

## Purpose
To maintain consistent structure, tone, and format across all published materials — including project case studies, journal entries, and content updates.

---

## Available Templates

### 1. `project_template.md`
**Use for:** Documenting projects, system builds, or case studies.  
**Recommended location:** `/docs/projects/`

**How to use:**
1. Copy `project_template.md` into `/docs/projects/`.  
2. Rename it appropriately (e.g., `project_name.md`).  
3. Fill in each section with project details — problem, approach, implementation, and insights.  
4. Commit, rebuild, and verify publication via:
   ```bash
   mkdocs serve
   ```

---

### 2. `post_template.md`
**Use for:** Writing journal posts, updates, or reflective essays.  
**Recommended location:** `/docs/blog/posts/`

**How to use:**
1. Copy `post_template.md` into `/docs/blog/posts/`.  
2. Rename it using the convention `YYYYMMDD_slug.md` (e.g., `20251111_phase5_intro.md`).  
3. Complete the sections — introduction, main content, and takeaways.  
4. Commit and rebuild the site.

---

## 🧩 Debugging & Build Tools

When working with MkDocs and Material themes, use the following commands for troubleshooting and validation:

| Purpose | Command |
|----------|----------|
| Build documentation | `mkdocs build` |
| Serve locally with live reload | `mkdocs serve` |
| Verbose build (show plugin and template traces) | `mkdocs build --verbose` |
| Clean old builds | `mkdocs build --clean` |
| Check site structure depth | `tree -L 3 -I '.venv|__pycache__|site'` |
| Verify Netlify configuration syntax | `toml-lint netlify.toml` |

---

## Version
**Templates Version:** v0.5.0  
**Maintained by:** Nicholas Dana  
**Last Updated:** 2025-11-11  
**Associated Phase:** Phase 5 — Content Cohesion & Brand Alignment