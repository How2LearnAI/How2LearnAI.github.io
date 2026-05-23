# Contributing to Learn AI

Thanks for your interest in improving Learn AI! This project is the source for the [how2learnai.github.io](https://how2learnai.github.io) tutorial site, built with MkDocs Material.

## Quick start

```bash
# 1. Fork and clone
git clone https://github.com/<your-username>/How2LearnAI.github.io.git
cd How2LearnAI.github.io

# 2. Install build dependencies (Python 3.10+)
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. Run the site locally
mkdocs serve
# open http://127.0.0.1:8000
```

The dev server live-reloads on save.

## What kinds of contributions are welcome?

- **Content fixes** — typos, broken links, outdated code in tutorials
- **New tutorials** — add a `.md` file and wire it into the `nav:` section of `mkdocs.yml`
- **Bug reports** — open an issue with steps to reproduce, expected vs. actual
- **Improvements to existing tutorials** — clearer explanations, better diagrams, modernized code

## Repository layout

```
docs/                  Tutorial content (.md and supporting images)
├── deep_learning/     Deep learning tutorials
├── language_model/    LLM, RAG, multi-modal
├── machine_learning/  GPU/CPU ML (RAPIDS, scikit-learn)
├── programming/       Python, C++, Bash, etc.
├── data_engineering/  Cassandra, NoSQL
├── blog/              Blog posts (uses the mkdocs blog plugin)
└── assets/            Site-wide images, favicon

material/              Custom MkDocs Material theme overrides
mkdocs.yml             Site config — nav, theme, plugins, extensions
requirements.txt       Pinned Python build dependencies
.github/workflows/     CI build & deploy to GitHub Pages
```

## Workflow

1. Create a topic branch off `master`: `git checkout -b fix-typo-in-rnn-tutorial`
2. Make your change. If you touch `.md` content, run `mkdocs serve` and check the rendered page.
3. Run a clean build to catch warnings:
   ```bash
   mkdocs build --clean
   ```
   Address any `WARNING` lines (broken links, missing images, etc.).
4. Commit with a descriptive message and open a pull request.

## Style guidelines

- **Markdown** — use ATX headings (`#`, `##`), fenced code blocks with a language tag (` ```python `), and relative links between docs (`../intro.md`) so they survive renames.
- **Math** — wrap LaTeX in `\(...\)` for inline and `\[...\]` for display. MathJax is configured site-wide.
- **Images** — place under `docs/<section>/images/` and reference relatively. Optimize PNGs/JPGs before committing.
- **Notebooks** — `.ipynb` files live alongside their `.md` exports. Keep both in sync if you change one.

## Deployment

Pushes to `master` automatically build the site and deploy to GitHub Pages via `.github/workflows/deploy.yml`. You don't need to deploy manually — opening a PR is enough.

## Reporting issues

For bug reports include:
- The page URL where you saw the issue
- What you expected vs. what happened
- Browser/OS if it's a rendering issue

For broken code in tutorials, please include the library versions you used.

## Contact

For questions outside GitHub issues, reach out via [LinkedIn](https://www.linkedin.com/in/ijbo/).
