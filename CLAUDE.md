# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal portfolio/blog website for Luis Ronquillo, a Java developer. It is hosted via GitHub Pages at `luisronquillo.com` (CNAME configured). There is no build system, package manager, or backend — everything is plain HTML, CSS, and JavaScript served directly.

## Development

Open `index.html` directly in a browser to preview the site. No build step is required.

To preview locally with a simple server:
```bash
python3 -m http.server 8080
```

## Architecture

- **[index.html](index.html)** — Main page with sections: Projects, My Notes, About Me, and Footer. This is the site's entry point.
- **[blog-section/blog_entry.html](blog-section/blog_entry.html)** — Template/example for individual blog entries.
- **[css/style.css](css/style.css)** — Custom styles. Uses the Nord color palette via CSS variables (`--nord0` through `--nord6`). The `.mybackground` class applies the primary dark background (`--nord2: #3B4252`) used for the header, navbar, and footer.
- **[css/bootstrap.min.css](css/bootstrap.min.css)** — Bootstrap v5.3.3 (vendored locally).
- **[js/bootstrap.bundle.min.js](js/bootstrap.bundle.min.js)** — Bootstrap JS bundle v5.3.3 (vendored locally).
- **[js/.prettierrc](js/.prettierrc)** — Prettier config (applies to JS files in the `js/` directory).
- **[resources/](resources/)** — Downloadable files (CV PDF).
- **[img/](img/)** — Images, including project SVGs in `img/projects/` and blog images in `img/blog/`.

## Key Conventions

- Bootstrap Icons are loaded from CDN (`bootstrap-icons@1.11.3`). All other assets are vendored.
- The header, navbar, and footer share the `.mybackground` class (Nord dark background with white text).
- Blog entries live under `blog-section/` and use the same header/navbar/footer structure as `index.html`. CSS/JS paths inside `blog-section/` use `../css/` and `../js/` (parent-relative). `blog_entry.html` is the legacy template; `blog_1.html` is the current live entry format with the Inter font added.
- `index_old.html` and `css/style_old.css` are legacy files kept for reference.
- The `.debug` class in `style.css` (red outline) is a utility for layout debugging.
