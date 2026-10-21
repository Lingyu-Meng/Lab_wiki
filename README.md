# Lab Wiki

This is a Markdown-first lab handbook built with [Quarto](https://quarto.org/) and published as a static site on GitHub Pages. Contributors can edit the `.qmd` chapter files directly in GitHub; they contain ordinary Markdown and require no R, Python, or command-line tools. A GitHub Action rebuilds the site whenever a change is committed to `main`.

## Edit a chapter on GitHub

1.  Ask Lingyu to add you as a collaborator to the repository
2.  Open the chapter file you want to edit, for example `methods/fmri.qmd`.
3.  Choose the pencil icon (**Edit this file**) and change the Markdown text.
4.  Commit your change to `main`, or open a pull request for review.
5.  After the change reaches `main`, GitHub Actions rebuilds and publishes the wiki automatically. Check the **Actions** tab if the published page does not update.

You need write access to this repository to commit changes. The generated website is not edited directly; edit the source chapter instead.

## Edit a chapter locally

For contributors who prefer to work locally, you need to install [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). Ask Lingyu to add you as a collaborator to the repository. Then clone the repository, edit the chapter files, and commit your changes.

RStudio and GitHub Desktop are highly recommended for contributors who are not familiar with the command line. See [GitHub Desktop](https://desktop.github.com/) and [RStudio](https://posit.co/download/rstudio-desktop/) for installation instructions.

If you are using GitHub Desktop, you should open the repository 'Lab_wiki' in GitHub Desktop, then click clone to your local machine. After that, you can edit the chapter files in your favourite text editor (RStudio), and commit and push your changes back to GitHub.

Notice that if someone else has made changes to the repository since you last pulled, you may need to fetch the latest changes before you can push your own changes. GitHub Desktop will prompt you if this is necessary.

## Add a chapter

1.  Create a `.qmd` file in the relevant folder using ordinary Markdown.
2.  Add its path to the `chapters:` list in `_quarto.yml`. That list controls the sidebar order.
3.  Commit the new file and configuration change. The automatic build publishes the updated book.

For a normal content update, edit only the relevant chapter; no change to `_quarto.yml` is needed.

## Repository layout

- `_quarto.yml` — book settings and navigation.
- `index.qmd` — welcome page.
- `getting-started/`, `lab-basics/`, `methods/` — editable chapter sources.
- `references.bib` — shared bibliography.
- `.github/workflows/publish.yml` — automatic render and GitHub Pages deployment.
- `_book/` — generated website output. It is created by the workflow and intentionally excluded from Git.

## One-time GitHub Pages setup

After uploading this repository to GitHub:

1.  In the repository, open **Settings → Pages**.
2.  Under **Build and deployment**, set **Source** to **GitHub Actions**.
3.  Ensure Actions are enabled for the repository.

The first successful workflow run publishes the site. Find its address under **Settings → Pages**. Later commits to `main` update it automatically. No contributor needs to install Quarto or run a build locally.

The workflow currently watches the `main` branch. If the repository uses a different default branch, update the branch name in `.github/workflows/publish.yml`.

## Content conventions

- Mark uncertain information as **To confirm** rather than writing it as policy.
- Link official university, funder, facility, and ethics guidance wherever possible.
- Include an owner and last-checked date on procedures that can change.
- Do not add credentials, identifiable participant data, or information the repository audience is not authorized to access.
- Keep restricted documents elsewhere and link them only if readers have permission.
