# oneduck: rules for every agent working in this repo

A task prompt for a coding agent, plus a one-page site that serves it. The prompt describes how to build OneDuck, a local router in front of role-based sub-agents. Read first: `prompt.md` (the prompt, canonical) and `README.md`.

## Setup and gate
- No build, no dependencies, no tests, no CI workflow in the repo. It is plain Markdown and static HTML.
- Before every push, open `index.html` in a browser and click "Copy prompt". Check the page and the copy button still work. Not verified by any script in the repo.

## Layout
- `prompt.md`: the prompt as plain text. Phases: 0 assess, 1 design, 2 implement and test.
- `index.html`: the landing page. It embeds a copy of the prompt text in `<pre id="prompt">` with HTML escaping, and a button copies it to the clipboard.
- `emblem.jpg`: the page image.
- `.nojekyll`: tells GitHub Pages to skip Jekyll.

## Deploy
GitHub Pages serves the repo from the `main` branch, root folder (read from the repo's Pages settings, not from a file). There is no deploy workflow. A merge to `main` changes the live page and `prompt.md`. Deploys need full review first.

## Rules
- `prompt.md` and the text inside `index.html` are two copies of one prompt. Change both in the same commit and keep them equal.
- When you edit text inside `index.html`, escape `&`, `<`, `>` and quotes as the file already does.
- Do not add keys, hosts or account details to the prompt or the page. The repo is public.
- Never push to `main`. Open a PR. Stage files by name. No force-push, no amend of pushed commits.
