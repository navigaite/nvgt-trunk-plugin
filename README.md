# Navigaite Trunk Plugin

[![Trunk](https://img.shields.io/badge/Trunk-Powered-brightgreen)](https://trunk.io)
[![License](https://img.shields.io/badge/License-MIT-green)](./LICENSE)

A centralized [Trunk](https://trunk.io) plugin that standardizes linting, formatting, and security scanning across all
Navigaite projects.

## Overview

This plugin provides a unified set of linting rules, configurations, and actions that can be shared across multiple
repositories. By sourcing this plugin, repositories automatically inherit standardized development workflows and quality
controls.

## Features

- **40+ Linters**: Pre-configured for multiple languages and frameworks
- **Shared Configurations**: 19 centrally managed config files for all major tools
- **Runtime Environments**: Built-in support for Go, Node.js, Python, and Ruby
- **Git Hooks**: Pre-commit formatting and pre-push quality checks
- **Security Scanning**: Secret detection, vulnerability scanning, and SAST
- **CI/CD Integration**: Universal pipeline with automated weekly releases
- **Automated Updates**: Trunk tool versions are upgraded automatically via scheduled workflows

## Supported Languages & Tools

| Category                  | Tools                                                         |
| ------------------------- | ------------------------------------------------------------- |
| **JavaScript/TypeScript** | ESLint, Prettier, Stylelint, Biome                            |
| **Python**                | Ruff (linting + formatting + import sorting + security), MyPy |
| **Go**                    | gofmt, golangci-lint                                          |
| **Ruby**                  | RuboCop                                                       |
| **Rust**                  | rustfmt, Clippy                                               |
| **C/C++**                 | clang-format, clang-tidy                                      |
| **Shell**                 | ShellCheck, shfmt                                             |
| **Docker**                | Hadolint                                                      |
| **Infrastructure**        | Checkov, Terrascan, CFN-Lint, Buildifier                      |
| **Security**              | TruffleHog, Semgrep, Trivy, OSV-Scanner                       |
| **Data Formats**          | yamllint, taplo (TOML), sql-formatter, Prisma                 |
| **Documentation**         | markdownlint, markdown-link-check                             |
| **CI/Config**             | actionlint, Renovate, dotenv-linter                           |
| **Images**                | oxipng, SVGO                                                  |

## Usage

### Adding to a Repository

1. Install the [Trunk CLI](https://docs.trunk.io/code-quality/setup-and-installation)
2. Initialize Trunk in your repository:
   ```bash
   trunk init
   ```
3. Add this plugin to your `.trunk/trunk.yaml`:
   ```yaml
   plugins:
     sources:
       - id: navigaite
         uri: https://github.com/navigaite/nvgt-trunk-plugin
         ref: v5.0.25
   ```
4. Run `trunk check` to validate

### For New Projects

Copy the example configuration from [`examples/trunk.yaml`](examples/trunk.yaml) to `.trunk/trunk.yaml` and adjust as
needed. Disable linters that don't apply to your stack.

### For CI/CD Integration

Use the Navigaite universal pipeline. See [`examples/github-actions-ci.yaml`](examples/github-actions-ci.yaml) for a
ready-to-use workflow, and [`examples/pipeline.yaml`](examples/pipeline.yaml) for the pipeline configuration.

## Shared Configurations

All configurations are exported from the `configs/` directory:

| Config               | Tool         | Purpose                                                        |
| -------------------- | ------------ | -------------------------------------------------------------- |
| `.prettierrc`        | Prettier     | JS/TS formatting (120 char width, single quotes)               |
| `biome.json`         | Biome        | JS/TS linting and formatting                                   |
| `ruff.toml`          | Ruff         | Python linting (replaces black, isort, pylint, bandit, flake8) |
| `.stylelintrc.json`  | Stylelint    | CSS/SCSS linting with Tailwind support                         |
| `.yamllint.yaml`     | yamllint     | YAML validation                                                |
| `.markdownlint.yaml` | markdownlint | Markdown linting                                               |
| `.shellcheckrc`      | ShellCheck   | Shell script linting                                           |
| `.checkov.yaml`      | Checkov      | IaC security scanning                                          |
| `.hadolint.yaml`     | Hadolint     | Dockerfile linting                                             |
| `rustfmt.toml`       | rustfmt      | Rust formatting                                                |
| `knip.json`          | Knip         | Unused code detection (JS/TS)                                  |
| `.cspell.json`       | CSpell       | Spell checking (EN + DE)                                       |
| `svgo.config.mjs`    | SVGO         | SVG optimization                                               |

## Actions

The following Trunk actions are enabled by default:

| Action                    | Trigger    | Purpose                                |
| ------------------------- | ---------- | -------------------------------------- |
| `trunk-fmt-pre-commit`    | Pre-commit | Format staged files automatically      |
| `trunk-check-pre-push`    | Pre-push   | Run full quality checks before pushing |
| `trunk-upgrade-available` | Background | Notify when upgrades are available     |
| `trunk-cache-prune`       | Background | Automatic cache maintenance            |

## CI/CD Workflows

| Workflow                | Schedule         | Purpose                                   |
| ----------------------- | ---------------- | ----------------------------------------- |
| **CI Pipeline**         | Push/PR to main  | Universal pipeline (lint, security)       |
| **Trunk Upgrade**       | Mon/Fri 8 AM UTC | Auto-upgrade linter versions              |
| **Weekly Release**      | Monday 9 AM UTC  | Create release with changelog             |
| **Automerge**           | On PR events     | Auto-merge labeled PRs                    |
| **Nightly Maintenance** | Daily 2 AM UTC   | Cleanup, security audit, dependency check |

## Runtimes

| Runtime | Version |
| ------- | ------- |
| Go      | 1.23.6  |
| Node.js | 22.16.0 |
| Python  | 3.13.3  |
| Ruby    | 3.4.2   |

## Contributing

1. Fork this repository
2. Make your changes
3. Test with `trunk check`
4. Submit a pull request

## License

[MIT](LICENSE)
