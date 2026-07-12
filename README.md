# jose-nino.com

Personal site — landing page, blog, and projects. Built with [Astro](https://astro.build), [Tailwind CSS](https://tailwindcss.com), and Markdown. Deployed to GitHub Pages at the custom domain `jose-nino.com`.

## Commands

```sh
npm install
npm run dev       # localhost:4321, live reload
npm run build     # outputs to ./dist
npm run preview   # serve the production build locally
```

## Writing a blog post

Add a Markdown file to `src/content/blog/`:

```md
---
title: "Post title"
description: "One-sentence summary, used on the blog index and in <meta description>."
date: 2026-01-01
tags: ["tag-one", "tag-two"]
draft: false
---

Post body in Markdown.
```

Set `draft: true` to keep a post out of the blog index and homepage while it's still being written.

## Adding a project

Add a Markdown file to `src/content/projects/`:

```md
---
title: "Project name"
description: "One-sentence summary shown on the card."
stack: ["TypeScript", "Astro"]
repoUrl: "https://github.com/janino163/example"
liveUrl: "https://example.com"
date: 2026-01-01
---
```

`repoUrl`, `liveUrl`, and `date` are optional. The projects page renders cards from frontmatter only — the Markdown body isn't currently displayed.

## Deployment

Pushing to `master` triggers `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages. The repo's **Settings → Pages → Build and deployment → Source** must be set to **GitHub Actions** for this to work.

The custom domain is set via `public/CNAME`, which Astro copies into the build output automatically.
