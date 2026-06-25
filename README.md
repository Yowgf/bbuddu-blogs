# bbuddu blog content

Posts for the [bbuddu](https://bbuddu.com) blog. Non-technical editors manage this
repo through **Sveltia CMS** at <https://bbuddu.com/blog/admin> — you rarely touch
these files by hand.

This is a **template**: copy its contents into a new **public** GitHub repo (the
"content repo"), then follow the setup below. Public means the app reads it with no token
and images load directly from GitHub.

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

## One-time setup

1. **Create a public repo** from this template; set its `owner/name` + branch in the
   bbuddu frontend (`NEXT_PUBLIC_BLOG_REPO`, `NEXT_PUBLIC_BLOG_BRANCH`) and in
   `app/frontend/public/blog/admin/config.yml`.
2. **No read token required** (the repo is public). Optional: if you ever see GitHub
   rate-limit errors, set a no-scope PAT on the app Worker via
   `wrangler secret put GITHUB_CONTENT_TOKEN`.
3. **Instant publish** — add this repo's `REVALIDATE_SECRET` (same value as the app
   Worker's secret) as an **Actions secret** here, so `revalidate.yml` can call the
   site on each push.
4. **Editor access** — anyone who should publish needs **write** access to this repo
   (that, plus GitHub OAuth, is what gates <https://bbuddu.com/blog/admin>). The repo is
   readable by anyone, but only collaborators can commit/publish.
