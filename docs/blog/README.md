# Builder Hub Blog — Internal Reference

This document describes how the **Builder Hub Journal (Blog)** is organized, configured, and maintained within the MkDocs Material environment.

---

## 1. Directory Layout

```
docs/
└── site/
    └── blog/
        ├── index.md
        ├── posts/
        │   └── YYYYMMDD_post-title.md
        └── README.md  ← (this file)
```

- `index.md` — serves as the main Journal landing page.
- `posts/` — contains all individual blog entries, each using YAML frontmatter.
- `README.md` — this internal documentation.

---

## 2. Blog Configuration

The Builder Hub blog uses **Material for MkDocs**’ built-in `blog` plugin (not `mkdocs-blog-plugin`).

```
plugins:
  - search
  - tags
  - git-revision-date-localized:
      enable_creation_date: true
  - blog:
      blog_dir: site/blog
      post_dir: site/blog/posts
```

MkDocs automatically generates:

- An index page with post listings.
- Individual post pages under `/blog/<slug>/`.
- Tag and category pages (if `tags:` and `category:` fields are defined).

---

## 3. Post Structure Template

Each post should begin with YAML frontmatter followed by Markdown content. Use the following format as a guide:

```
---
title: "[Post Title]"
date: [YYYY-MM-DD]
category: [Reflection / Update / Development / Insight]
tags:
  - [Brand]
  - [Development]
  - [Data Science]
---

## Introduction
Introduce the post’s context, motivation, or trigger.  
Keep the tone reflective and structured — connect the immediate story to a larger system or principle.

## Main Content
Write in your natural *Builder* tone: precise, reflective, low-fluff.  
Favor narrative paragraphs over bullet lists unless listing insights, lessons, or sequential steps.

## Takeaways
Summarize the key learnings, outcomes, or open questions that emerged from this work or reflection.

---
*Template: Journal Entry Framework (BrandBuilder v0.4.2)*  
*(Note: Verify YAML frontmatter syntax before publishing.)*
```

---

## 4. Authoring Notes

- Posts are detected automatically; no need to manually list them in navigation.
- `tags:` and `category:` metadata enable automatic grouping and filtering.
- Local testing:

  ```
  mkdocs serve
  ```
  
  Then open [http://127.0.0.1:8000/site/blog/](http://127.0.0.1:8000/site/blog/)

---

**Maintained by:** Nicholas Dana  
**Version:** v0.4.2  
**Last Updated:** 2025-10-26