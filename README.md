# flurgles.github.io — dock6 Development Updates

This site tracks development progress on my [dock6](https://github.com/flurgles/dock6) branch.

## Local Development

```bash
# Install dependencies
bundle install

# Start the dev server
bundle exec jekyll serve

# Build the site
bundle exec jekyll build
```

The site is served at `http://localhost:4000`.

## Adding a post

Create a new file in `_posts/` named `YYYY-MM-DD-your-title.md` with this front matter:

```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS -0700
tags: [tag1, tag2]
---
```

Write the body in markdown. Use `<!--more-->` to set where the excerpt cuts off
on the home page.

## Deploy

Push to the `main` branch — GitHub Pages builds and deploys automatically.