# Git command-line basics

These examples assume you are inside a cloned repository with a remote named `origin` and a base branch named `main`. Substitute names when your repository uses different ones.

## Start a focused change

```sh
git status
git switch -c docs/add-a-note
```

`git switch -c` creates and switches to a new branch. Use a short branch name that describes one change.

## Review and record the change

```sh
git status
git add path/to/the-file.md
git diff --cached
git commit -m "docs: add a focused note"
git log --oneline -5
```

`git add` stages the named file, and `git diff --cached` shows what is staged for the next commit. Review it before committing; do not stage secrets, credentials, or unrelated files.

## Publish your branch for a pull request

```sh
git push -u origin docs/add-a-note
```

This publishes the branch to the configured `origin` remote. Confirm the repository and branch before pushing, then open a pull request and describe the single topic it contains.

## References

- [Git tutorial](https://git-scm.com/docs/gittutorial)
- [Git: recording changes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
- [Git: branches in a nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
