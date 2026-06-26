# bbuddu blog content

Posts for the [bbuddu](https://bbuddu.com) blog. Editors manage this repo
through **Sveltia CMS** at <https://bbuddu.com/blog/admin> — you rarely touch
these files by hand.

## Layout

```
posts/        one Markdown file per post — filename (minus .md) is the URL slug
media/        images uploaded by the CMS (created on first upload)
.github/workflows/revalidate.yml   pings the live site to publish instantly
```

## Post format (YAML frontmatter + Markdown body)

```markdown
---
title: Choosing a Season
date: 2026-05-01
excerpt: When to marry abroad — and when not to.   # optional
cover: /media/season.jpg                            # optional
---

Body text in **Markdown**…
```

The live URL is `/blog/post/<filename-without-.md>`.
