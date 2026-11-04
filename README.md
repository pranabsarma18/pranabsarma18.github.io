# Pranab Sarma Portfolio

This repository contains the source and generated files for [Pranab Sarma's portfolio](https://pranabsarma.me). It publishes a portfolio page and a resume page as static HTML. Both pages are generated from the same JSON data file, so profile and experience details stay consistent.

## Features

- Data-driven content stored in `portfolio.json`.
- Portfolio and resume pages generated with Python and Jinja2.
- Work experience, projects, education, skills, interests, and languages.
- Social links with SVG icons embedded in the generated HTML.
- Responsive layouts, page metadata for link previews, favicon, and web app manifest.
- Static output that can be hosted without a web server or database.

## Project structure

| Path | Purpose |
| --- | --- |
| `portfolio.json` | Main source of portfolio and resume content. |
| `generate_portfolio.py` | Reads the JSON, loads social SVGs, and generates the pages. |
| `index_template.html` | Jinja2 template for the portfolio page. |
| `resume_template.html` | Jinja2 template for the resume page. |
| `index.html` | Generated portfolio page. |
| `resume.html` | Generated resume page. |
| `css/` | Normalize, layout, portfolio, and print styles. |
| `img/` | SVG icons used by the social links. |
| `portfolio_media/` | Portfolio images, including the profile photo. |
| `favicon.ico`, `icon.png`, `icon-192x192.png`, `icon-512x512.png` | Browser, Apple touch, and web app icons. |
| `site.webmanifest` | Web app name and icon metadata. |
| `requirements.txt` | Python package versions needed by the generator. |
| `robots.txt` | Allows search engine crawlers to access the site. |

## Requirements

- Python 3.11 or newer.
- `pip`.

## Set up and generate the site

Run these commands from the repository root:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python generate_portfolio.py
```

The generator writes `index.html` and `resume.html` in the repository root. Open either file in a browser to preview the generated pages locally.

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Then run the same `pip install` and generation commands, using `python` in place of `python3` if needed.

## Updating content

1. Edit `portfolio.json`.
2. Run `python generate_portfolio.py` from the repository root.
3. Review the generated `index.html` and `resume.html`.
4. Commit the JSON, template, style, or generated page changes that apply.

The generator expects paths in `portfolio.json`, including `image_path` and social `svg_path` values, to be relative to the repository root. Social SVG files are read during generation and embedded into the page.

Skills and languages are plain text lists. Interest entries can include `summary` and, when applicable, `project_title` and `project_url` to show a related project link.

## Deployment

The generated pages are static files and can be deployed to GitHub Pages or another static host. For GitHub Pages, configure the repository to publish the root of the `main` branch. The canonical site URL used for social metadata is set by `base_url` in `portfolio.json`.

## Credits

This project is based on and adapted from Corey Schafer's portfolio generator and tutorial:

- [Python Tutorial: Generate a Web Portfolio and Resume from One JSON File](https://www.youtube.com/watch?v=ECt0TAl41Zk) by Corey Schafer.
- [Corey Schafer's `portfolio_generator` repository](https://github.com/CoreyMSchafer/portfolio_generator), which provides the original JSON-driven portfolio and resume generator.

The project has been customized with its own content, templates, styles, and generated pages. See [LICENSE](LICENSE) for the MIT license and copyright notices.
