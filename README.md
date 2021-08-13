<h1 align="center">ESLint PR review</h1><p align="center"><a href="https://github.com/rpkak/ESLint-PR-review/actions/workflows/test.yml"><img src="https://github.com/rpkak/ESLint-PR-review/actions/workflows/test.yml/badge.svg"/></a> <a href="https://github.com/rpkak/ESLint-PR-review/issues"><img src="https://img.shields.io/github/issues/rpkak/ESLint-PR-review?style=flat-square"/></a> <a href="https://github.com/rpkak/ESLint-PR-review/pulls"><img src="https://img.shields.io/github/issues-pr/rpkak/ESLint-PR-review?style=flat-square"/></a> <a href="https://github.com/rpkak/ESLint-PR-review/stargazers"><img src="https://img.shields.io/github/stars/rpkak/ESLint-PR-review?style=flat-square"/></a> <a href="https://github.com/rpkak/ESLint-PR-review/releases"><img src="https://img.shields.io/github/v/release/rpkak/ESLint-PR-review?style=flat-square"/></a> <a href="https://github.com/rpkak/ESLint-PR-review/releases"><img src="https://img.shields.io/github/v/release/rpkak/eslint-pr-review?include_prereleases&label=pre-release&style=flat-square"/></a></p>


A simple workflow, that creates pull request reviews for ESLint problems

## Inputs

### `project-root`

The path to the directory, which includes files like `package.json` or `.eslintrc.json`.

Default: `.`

### `src`

What you want to lint. Relative to `project-root`.

Default: `.`

Example: `src` (Lints every lintable file in the source folder)

### `github-token`

The GitHub Token of the repository. It is needed for reviewing the Pull Requests.

**Required**

Example: `${{ secrets.GITHUB_TOKEN }}`

### `eslint-format`

The [ESLint Format](https://eslint.org/docs/user-guide/formatters/) to print the linting result to the GitHub Actions log

Default: `stylish`

Examples: `codeframe`, `compact`, `table`, `tap`, `unix`, `visualstudio`

### `approve-mode`

0 for dismissing change-requests, 1 for approving after change-requests, 2 for approving always if ESLint doesn't fail

Default: `0`

### `extensions`

Comma separated list of file the fileendings, ESLint should lint.

Default: `js,jsx,ts,tsx`

### `node-version`

Version of node for project packages.

Default: `node` (latest version)

Examples: `12`, `v10.12`

## Example usage:
```yaml
name: ESLint PR review

on:
  push:

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: rpkak/ESLint-PR-review@latest
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          src: src
          eslint-format: table
```

## Example output:

![example](https://user-images.githubusercontent.com/67059904/116257821-acad1000-a774-11eb-82e4-edaef33a4c97.png)

## Infos

Use `rpkak/ESLint-PR-review@latest` to get the latest none development version ESLint PR review.

Please report everything like bugs by creating an [issue](https://github.com/rpkak/ESLint-PR-review/issues/new/choose).

Version: v1.2.1

by [rpkak](https://github.com/rpkak)
