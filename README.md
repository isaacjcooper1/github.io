
# GitHub Pages Portfolio (Jekyll + Corporate Style)

This starter takes the simple corporate HTML you liked and adds **Jekyll** so you can:

- Use a **theme** (here: `jekyll-theme-minimal`) and Jekyll features.
- Create pages in **Markdown** and share a common layout.
- Keep your custom corporate CSS.

## How to Use

1. Create a public repo named `your-username.github.io`.
2. Upload these files to the repo root and commit.
3. Visit `https://your-username.github.io` (first publish can take ~1 minute).

## Customize
- Update `_config.yml` with your `url`, `title`, and switch `theme:` if desired.
- Replace placeholders (`your-github-username`, `your-linkedin-handle`, email) in `index.md`.
- Replace the resume at `assets/resume/Isaac-Cooper-Resume.pdf`.
- Add new case studies by duplicating files in `/projects` and updating links.

## Change Theme
GitHub Pages supports built-in themes (Minimal, Cayman, Slate, etc.).
- Edit `_config.yml` → `theme: jekyll-theme-slate` (example), commit, and Pages will rebuild.
- Or use `remote_theme:` to load other public themes.

## Local Preview (optional)
If you want to run locally, install Ruby + Bundler, then:
```
bundle init # create Gemfile
# add: gem 'github-pages', group: :jekyll_plugins
bundle install
bundle exec jekyll serve
```
Visit `http://localhost:4000`.

## License
Use freely. No attribution required.
