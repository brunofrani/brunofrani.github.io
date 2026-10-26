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
| `_posts/` | Blog posts (optional — the Writing section appears once the first one exists) |
| `_layouts/`, `_includes/` | Page templates |
| `assets/css/site.css` | All styling, light and dark |

## Adding a project

1. Create `_projects/<name>.md` with front matter like `_projects/tilt-runner.md`: `title`, `tagline`, `platform`, `status`, `order`, and optionally `icon`, `accent` and `app_store_url`.
2. Put its icon in `assets/images/projects/`.
3. For legal pages, add Markdown files under `projects/<name>/` with `layout: legal` and `project: <name>`. They are linked from the project page automatically.

## Tilt Runner legal pages

- Privacy Policy: <https://brunofrani.github.io/projects/tilt-runner/privacy/>
- Terms of Service: <https://brunofrani.github.io/projects/tilt-runner/terms/>
- Support page (for App Store Connect): <https://brunofrani.github.io/projects/tilt-runner/>

When the game's data handling changes (a new SDK, a new kind of data), update the Privacy Policy and its `last_updated` date in the same release.
