# Contributing to Actions Playground

Thank you for your interest in contributing to this project! This document provides guidelines and instructions for contributing.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your changes
4. Make your changes
5. Test your changes
6. Submit a pull request

## Development Setup

### Pre-commit Hooks

This repository uses [pre-commit](https://pre-commit.com/) to ensure code quality and consistency. All contributors must set up pre-commit hooks before submitting changes.

#### Installation

1. Install pre-commit:

   ```bash
   pip install pre-commit
   ```

2. Install the git hooks:

   ```bash
   pre-commit install
   ```

#### Usage

Once installed, the hooks will run automatically on `git commit`. To run manually on all files:

```bash
pre-commit run --all-files
```

To run on specific files:

```bash
pre-commit run --files <file1> <file2> ...
```

#### Hooks Included

##### General Checks

- Trailing whitespace removal
- End of file fixing
- YAML syntax validation
- Large file detection
- Merge conflict detection
- Case conflict detection
- Mixed line ending detection

##### Language-Specific Hooks

**GitHub Actions**
- **actionlint**: Lints GitHub Actions workflow files

**YAML**
- **yamlfmt**: Formats YAML files

**Markdown**
- **markdownlint**: Lints Markdown files

**Python**
- **yapf**: Google's Python code formatter

**JavaScript/Node.js**
- **eslint**: Linter for JavaScript/TypeScript files

**Go**
- **golangci-lint**: Comprehensive Go linter

**Shell Scripts**
- **shellcheck**: Lints shell scripts

##### Security and Quality

- **gitleaks**: Detects secrets and credentials
- **codespell**: Checks for common spelling mistakes

#### Skipping Hooks

To skip hooks for a specific commit (not recommended):

```bash
git commit --no-verify
```

#### Updating Hooks

To update all hooks to their latest versions:

```bash
pre-commit autoupdate
```

## Continuous Integration

### GitHub Actions Workflows

The repository uses GitHub Actions for automated testing and linting:

#### Pre-commit Checks (`.github/workflows/pre-commit.yml`)

Runs on all pull requests and pushes to main branch. Executes all pre-commit hooks to ensure code quality.

#### GitHub Actions Linting (`.github/workflows/lint-github-actions.yml`)

Runs on pull requests that modify files in the `.github/` directory. Includes:

- **actionlint**: GitHub Actions workflow linting
- **OSSF Scorecard**: Security best practices analysis
- **Snyk**: Infrastructure as Code security scanning
- **Octoscan**: GitHub Actions security scanning

Results are uploaded to the Security tab via SARIF format.

## Pull Request Guidelines

1. **Keep changes focused**: Each PR should address a single concern
2. **Write clear commit messages**: Use descriptive commit messages that explain what and why
3. **Test your changes**: Ensure all pre-commit hooks pass before submitting
4. **Update documentation**: If your changes affect usage, update relevant documentation
5. **Follow coding standards**: All code must pass the configured linters and formatters

## Code Style

This project uses automated formatters and linters to maintain consistent code style:

- **Python**: Formatted with `yapf` (Google style)
- **JavaScript/TypeScript**: Linted with `eslint`
- **Go**: Linted with `golangci-lint`
- **YAML**: Formatted with `yamlfmt`
- **Markdown**: Linted with `markdownlint`
- **Shell scripts**: Linted with `shellcheck`

All formatting and linting rules are enforced via pre-commit hooks.

## Questions or Issues?

If you have questions or run into issues while contributing:

1. Check existing issues to see if your question has been answered
2. Review the documentation in this repository
3. Open a new issue with a clear description of your question or problem

## License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project.
