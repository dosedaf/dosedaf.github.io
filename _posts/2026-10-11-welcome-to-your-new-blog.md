---
layout: post
title: "Welcome to your new blog"
categories: meta
---

This post exists to show off every element of the theme, and to double as a
short manual for writing posts here. Edit it, or delete it whenever you like.

<!--more-->

## How to write a post

Create a file in `_posts/` named with today's date, like this:

```text
_posts/2026-10-11-my-first-post.md
```

The filename sets the date and the URL, so this one lives at
`/blog/2026/10/11/my-first-post/`. The file itself starts with a little header
called *front matter*, then just Markdown:

```yaml
---
layout: post
title: "My First Post"
categories: tech
---

Regular **Markdown** from here on.
```

Drop it in `_posts/`, save, refresh the browser &mdash; the running server
rebuilds automatically. Push to GitHub when you're happy and it's live.

### Drafts

Put unfinished posts in a `_drafts/` folder *without* a date in the filename.
They show up when you run `bundle exec jekyll serve --drafts`, and are never
published until you move them to `_posts/` (adding the date).

## What you can put in a post

### Code

Inline code like `git log --oneline` gets the boxed look, and fenced blocks get
the classic cream-and-syntax-colored treatment:

```ruby
def greet(name)
  puts "Hello, #{name}!"   # says hi
end

greet("world")
```

### Quotes

> Blockquotes are italic with a soft left border, like this. Great for pulling
> a line out of something you're discussing.

### Lists

1. Ordered lists
2. and unordered lists
3. both work

- with nested
  - items too

### Everything else

[Links](https://jekyllrb.com/docs/posts/), *italics*, **bold**, images with
`![alt text](/images/something.png)`, and tables:

| Command | What it does |
|---------|--------------|
| `bundle exec jekyll serve` | Preview at `localhost:4000` |
| `bundle exec jekyll serve --drafts` | Preview including drafts |

## The teaser cut

Notice how the homepage only showed the first bit of this post? That's the
`<!--more-->` marker up top. Everything above it is the teaser, followed by a
**Read on &rarr;** button. Leave it out and the homepage shows the whole post.
