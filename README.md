# Personal website

A minimal Hugo site with Home, Research, Essays, Career, and Wiki pages.
No external theme, JavaScript, or Node dependencies are required.

## Run locally

Install Hugo 0.158.0 or newer (verified with 0.162.1), then run from this directory:

```sh
hugo server -D
```

Open <http://localhost:1313/>. Hugo reloads the site when you edit files.
The `-D` flag includes draft pages for local previews.

## Edit content

- `content/_index.md`: home page text.
- `content/research/_index.md`: Research landing page.
- `content/essays/_index.md`: Essays landing page.
- `content/career/_index.md`: Career landing page.
- `content/wiki/_index.md`: Wiki landing page.

Each section can contain additional Markdown pages. For example:

```sh
hugo new content essays/my-first-essay.md
hugo new content wiki/example-note.md
```

New pages start with `draft = true`. Change this to `false` when ready to
include them in a production build. Published pages appear automatically on
their section's landing page. Use the front matter `weight` field to control
ordering; pages with equal weight sort by date, newest first.

## Change configuration and appearance

- `hugo.toml`: site title, description, base URL, and navigation.
- `layouts/baseof.html`: shared HTML structure.
- `layouts/_partials/navigation.html`: shared navigation.
- `layouts/home.html`: home page layout.
- `layouts/section.html`: section landing pages and their child-page lists.
- `layouts/page.html`: individual content pages.
- `static/css/main.css`: minimal styles, ready for later design work.

The layouts follow Hugo's [template structure](https://gohugo.io/templates/types/).
Put downloadable files and images in `static/`; Hugo copies them into the
generated site. For example, `static/files/cv.pdf` becomes `/files/cv.pdf`.

## Build

```sh
hugo --minify
```

Hugo generates the static website in `public/`, which is ignored by Git.
Before publishing, replace the placeholder `baseURL` in `hugo.toml` with the
final website URL, and update the site title. Hosting is not configured yet.
