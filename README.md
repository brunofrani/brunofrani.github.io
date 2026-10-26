# brunofrani.github.io

Personal site and home for my side projects, built with [Jekyll](https://jekyllrb.com) and deployed to GitHub Pages by [`.github/workflows/jekyll.yml`](.github/workflows/jekyll.yml) on every push to `master`.

## Run it locally

```sh
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Layout

| Path | What it is |
| --- | --- |
| `_config.yml` | Site title, description, author and contact email |
| `index.html` | Home page |
| `_projects/` | One Markdown file per project, published at `/projects/<name>/` |
| `projects/<name>/` | A project's own extra pages, such as its Privacy Policy and Terms |
| `_posts/` | Articles, published at `/articles/<title>/` (listed under Articles in the top bar; the home page section appears once the first one exists) |
| `_layouts/`, `_includes/` | Page templates |
| `assets/css/site.css` | All styling, light and dark |

## Adding a project

1. Create `_projects/<name>.md` with front matter like `_projects/tilt-runner.md`: `title`, `tagline`, `platform`, `status`, `order`, and optionally `icon`, `accent` and `app_store_id` (which adds the download button and Safari's Smart App Banner).
2. Put its icon in `assets/images/projects/`.
3. For legal pages, add Markdown files under `projects/<name>/` with `layout: legal` and `project: <name>`. They are linked from the project page automatically.

## Writing an article

Create `_posts/YYYY-MM-DD-short-title.md`. The date sets the order and the
file name sets the URL (`/articles/short-title/`).

```markdown
---
title: How Tilt Runner turns tilt into motion
description: One or two sentences, shown in article lists and link previews.
project: tilt-runner   # optional: links the article to a project's page
image: /assets/images/articles/short-title/cover.png   # optional preview image
---

The first paragraph. Then Markdown as usual — headings, lists, tables, and
fenced code blocks (` ```swift `) with syntax highlighting.
```

Put images in `assets/images/articles/<short-title>/` and add them with
`![Description](/assets/images/articles/short-title/figure.png)`. For a
caption, use `<figure>` with an `<img>` and a `<figcaption>`.

To preview an unfinished article, put it in `_drafts/` (no date in the file
name) and run `bundle exec jekyll serve --drafts`. Drafts are never published.

## Tilt Runner legal pages

- Privacy Policy: <https://brunofrani.github.io/projects/tilt-runner/privacy/>
- Terms of Service: <https://brunofrani.github.io/projects/tilt-runner/terms/>
- Support page (for App Store Connect): <https://brunofrani.github.io/projects/tilt-runner/>

Set these as the Privacy Policy URL and Support URL in App Store Connect.

When the game's data handling changes (a new SDK, a new kind of data), update the Privacy Policy and its `last_updated` date in the same release.
