# intrusionjake.github.io

My cybersecurity journal — college, Hack The Box, homelab and certifications.
Built with [Jekyll](https://jekyllrb.com/) and the [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) theme,
deployed to GitHub Pages by GitHub Actions on every push to `main`.

## Writing a post

1. Copy a template from `templates/` into `_posts/` named `YYYY-MM-DD-title.md`.
2. Fill in the front matter (title, date, categories, tags) and write in Markdown.
3. Put images under `assets/img/` and reference them as `/assets/img/...`.
4. Commit and push — the site rebuilds automatically.

| Template | Use for |
| --- | --- |
| `templates/journal-entry.md` | Weekly/class journal, homelab notes |
| `templates/htb-writeup.md` | Hack The Box write-ups (**retired** boxes only) |
| `templates/cert-post.md` | Certification study plans & exam debriefs |

Certifications on the `/certifications/` page come from `_data/certs.yml`.

## Run locally

```bash
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://127.0.0.1:4000>.
