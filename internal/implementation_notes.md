

# Internal Implementation Notes

**Project:** ndana_bb — Builder Hub  
**Maintainer:** Nicholas Dana  
**Created:** November 2025  
**Purpose:** Consolidate detailed implementation learnings, debugging results, and configuration behaviors extracted from `phase_reviews.md`.  

> **Note:** This document currently houses both development and operational learnings (e.g., build, deployment, and configuration behavior). These topics may later be separated into dedicated internal files (`testing_notes.md`, `operations.md`) once patterns of maturity and stability are established.
**Visibility:** Internal reference only — excluded from published documentation.

---

## 1. CSS and Theming

### CSS Override Simplification (v0.4.5.1)
- Original `extra.css` contained redundant specificity and nested selectors (e.g., duplicated `body[data-md-color-scheme]` rules).  
- Simplified during Phase 4.5 refactor to hybrid model:
  - Retained theme-scoped selectors where color or contrast varied by mode.
  - Removed redundant layout and structure rules that duplicated Material defaults.  
- Verified consistent rendering in light/dark modes across Chrome, Safari, and Firefox.  
- Established rule: **use `body[data-md-color-scheme]` only for color or shadow overrides.**
- Confirmed late-loading of `extra.css` ensures brand color specificity wins against Material defaults.

### Hero Section Styling
- CSS refinements added in Phase 4.5.3 include:
  - Accent underline for `<h1>` header.
  - Consistent spacing and line-height for textual rhythm.
  - Subtle divider using `border-bottom` to structure page layout.
  - Responsive refinements for mobile with reduced vertical padding and balanced CTA spacing.  
- Visual testing confirmed consistent alignment with Brand OS color palette and responsive stability.

---

## 2. MkDocs Material Plugin Behavior

### Blog System and Taxonomy
- Material’s `blog` plugin dynamically generates `/blog/categories/` and `/blog/tags/` pages; explicit `nav` or stub files cause duplication.  
- **Correct configuration:**
  - Do not include manual nav entries for auto-generated taxonomy pages.
  - Remove stub Markdown files (e.g., `categories.md`, `tags.md`).
  - Metadata must use YAML list syntax for recognition (e.g., `categories: ['AI', 'Development']`).
- Categories confirmed functioning under Material v9.6.22 after clean rebuild.
- Tag rendering proved inconsistent due to `template` path references (`blog-post.html`) introduced by internal plugin logic—deferred for future version validation.

### MkDocs Configuration
- Plugin block:
  ```yaml
  - material/blog:
      blog_dir: blog
      post_dir: blog/posts
  ```
- Verified correct behavior only after moving blog folder from `docs/site/blog/` to `docs/blog/`.

### Theme Loading Order
- Verified `extra.css` loads after Material default styles (`main.css` and `palette.css`), ensuring custom overrides apply correctly.
- Confirmed theme palette alignment across rebuilds; no caching conflicts detected post v0.4.5 refactor.

---

## 3. Hero Layout Implementation

### Semantic Refactor
- Replaced Markdown + inline HTML hybrid with a semantic `<section>` structure for accessibility and maintainability.
- Added ARIA annotations:
  - `aria-label` for descriptive screen reader navigation.
  - `alt` text for the portrait image.
  - `aria-label` for CTA to clarify action.
- Ensures full compliance with accessible markup standards and screen reader behavior.

### Structural Guidelines
- `.hero-text`, `.hero-image`, and `.hero-cta` maintain separation of content concerns:
  - `hero-text`: textual content and lists.
  - `hero-image`: portrait or brand imagery.
  - `hero-cta`: calls to action.
- Flexbox layout ensures smooth wrapping and proportional spacing across devices.

---

## 4. Deployment and Environment Notes

### Netlify Integration
- Build configuration (Python 3.12) validated for MkDocs 1.6.x and Material 9.6.x.
- Added pip no-cache directive in `netlify.toml` for faster dependency resolution.
- TLS and custom domain (`builder.npdana.pro`) verified post DNS migration to Netlify-managed nameservers.
- Ensure Python version consistency between local virtualenv and Netlify environment to prevent dependency mismatches.

### Git & Version Control
- SSH authentication errors traced to cleared macOS keychain agent; resolved by re-adding private key via:
  ```bash
  ssh-add --apple-use-keychain ~/.ssh/id_ed25519
  ```
- `.venv/` excluded from repository via `.gitignore`.
- Established version tagging pattern: `vMAJOR.MINOR.BUGFIX` for consistency across `phase_reviews.md` and commits.

---

## 5. Known Issues / Deferred Work
- Tag rendering under Material blog plugin unreliable due to internal Jinja template resolution; revisit in Phase 5+.
- Visual depth enhancements (gradient, parallax) intentionally deferred.
- Accessibility/SEO enhancements pending evaluation for future milestone.
- Future improvement: Implement post excerpts on blog index via `<!-- more -->` markers or truncation logic.

---

**End of Notes**