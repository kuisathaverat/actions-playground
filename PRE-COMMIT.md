# Pre-commit Hooks Setup

This repository uses [pre-commit](https://pre-commit.com/) to ensure code quality and consistency.

## Installation

1. Install pre-commit:

   ```bash
   pip install pre-commit
   ```

2. Install the git hooks:

   ```bash
   pre-commit install
   ```

## Usage

Once installed, the hooks will run automatically on `git commit`. To run manually on all files:

```bash
pre-commit run --all-files
```

To run on specific files:

```bash
pre-commit run --files <file1> <file2> ...
```

## Hooks Included

### General Checks

- Trailing whitespace removal
- End of file fixing
- YAML syntax validation
- Large file detection
- Merge conflict detection
- Case conflict detection
- Mixed line ending detection

### Language-Specific Hooks

#### GitHub Actions

- **actionlint**: Lints GitHub Actions workflow files

#### YAML

- **yamlfmt**: Formats YAML files

#### Markdown

- **markdownlint**: Lints Markdown files

#### Python

- **yapf**: Google's Python code formatter

#### JavaScript/Node.js

- **eslint**: Linter for JavaScript/TypeScript files

#### Go

- **golangci-lint**: Comprehensive Go linter

#### Shell Scripts

- **shellcheck**: Lints shell scripts

### Security and Quality

- **gitleaks**: Detects secrets and credentials
- **codespell**: Checks for common spelling mistakes

## Skipping Hooks

To skip hooks for a specific commit (not recommended):

```bash
git commit --no-verify
```

## Updating Hooks

To update all hooks to their latest versions:

```bash
pre-commit autoupdate
```

## GitHub Actions Integration

The `.github/workflows/lint-github-actions.yml` workflow runs similar checks on pull requests that
modify files in the `.github/` directory, including:

- **actionlint**: GitHub Actions workflow linting
- **OSSF Scorecard**: Security best practices analysis
- **Snyk**: Infrastructure as Code security scanning
- **Octoscan**: GitHub Actions security scanning

These automated checks help maintain code quality and security standards.
