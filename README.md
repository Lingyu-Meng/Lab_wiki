# Lab Wiki

This is a Markdown-first lab handbook built with [Quarto](https://quarto.org/) and published as a static site with GitLab Pages. Contributors can edit the `.qmd` chapter files directly in GitLab; they contain ordinary Markdown and require no R, Python, Quarto, or command-line tools on the contributor's computer. GitLab CI renders the complete book and publishes it whenever a change reaches the default branch.

## Edit a chapter in GitLab

1. Open the chapter file you want to change, for example `methods/fmri.qmd`.
2. Select **Edit** and change the Markdown text.
3. Commit directly to the default branch, or create a branch and merge request for review.
4. After the change reaches the default branch, open **Build → Pipelines** to see the render and deployment. The site address is shown under **Deploy → Pages** after a successful deployment.

You need permission to commit changes to the repository. Edit the source chapter; do not edit generated HTML.

## Add a chapter

1. Create a `.qmd` file in the relevant folder using ordinary Markdown.
2. Add the file path to the `chapters:` list in `_quarto.yml`. That list controls the sidebar order.
3. Commit the new file and configuration change. The CI pipeline rebuilds and publishes the book.

For a normal content update, edit only the relevant chapter; no configuration change is needed.

## Repository layout

- `_quarto.yml` — book settings and navigation.
- `index.qmd` — welcome page.
- `getting-started/`, `lab-basics/`, `methods/` — editable chapter sources.
- `references.bib` — shared bibliography.
- `.gitlab-ci.yml` — automatic Quarto render and GitLab Pages deployment.
- `public/` — generated website output. The CI pipeline creates it; it is intentionally excluded from Git.

## GitLab Pages setup

The repository must have GitLab Pages and a CI runner enabled. On GitLab Self-Managed, the GitLab administrator must enable the Pages service and configure its domain; project owners may also need to enable Pages under **Settings → General → Visibility, project features, permissions**. If the **Build → Pipelines** job does not start, ask the project or GitLab administrator whether CI runners and the Quarto container image are allowed.

The `pages` job in `.gitlab-ci.yml` runs on the default branch. It renders HTML into `public/` and publishes that directory. GitLab identifies the Pages site URL under **Deploy → Pages** after the first successful pipeline.

## Content conventions

- Mark uncertain information as **To confirm** rather than writing it as policy.
- Link official university, funder, facility, and ethics guidance wherever possible.
- Include an owner and last-checked date on procedures that can change.
- Do not add credentials, identifiable participant data, or information the repository audience is not authorized to access.
- Keep restricted documents elsewhere and link them only if readers have permission.
