# My Blog

Classic Octopress-style blog, built with Jekyll, deploys to GitHub Pages.

## Write a post

1. Create `_posts/2026-10-11-my-post.md` (date in the filename sets the date + URL)
2. Front matter + Markdown:

   ```yaml
   ---
   layout: post
   title: "My Post"
   categories: tech
   ---
   ```

3. Add `<!--more-->` where the homepage teaser should cut off
4. Save — the preview server rebuilds automatically

Unfinished posts go in `_drafts/` (no date in filename), preview with
`bundle exec jekyll serve --drafts`.

## Preview locally

```sh
bundle exec jekyll serve        # → http://localhost:4000
```

## Publish (GitHub Pages, user site)

1. Create a repo named `<username>.github.io`
2. Update `url:` in `_config.yml` to `https://<username>.github.io`
3. `git remote add origin git@github.com:<username>/<username>.github.io.git`
4. `git push -u origin main` — Pages builds it automatically

## Customize

- **Colors/palette:** everything is SCSS variables at the top of `css/main.scss`
- **Title, name, tagline:** `_config.yml`
- **Nav pages:** `_includes/navigation.html`
- **Sidebar:** `_includes/sidebar.html`
