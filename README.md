# 2k charity ride (Jekyll)

This repository is now set up as a Jekyll website.

## Run locally

1. Install Ruby and Bundler (if needed).
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Start the site:
   ```bash
   bundle exec jekyll serve
   ```
4. Open: http://127.0.0.1:4000

## Add a new post

Create a file in `_posts/` using this format:

`YYYY-MM-DD-your-title.md`

Example:

`_posts/2026-06-14-my-first-ride-update.md`

Post template:

```markdown
---
layout: post
title: "My first ride update"
date: 2026-06-14 09:00:00 +0000
categories: updates
---

Write your post content here.
```

That is all you need to do for publishing new posts.
