# Navigaite Trunk Plugin

[![Trunk](https://img.shields.io/badge/Trunk-Powered-brightgreen)](https://trunk.io)
[![Version](https://img.shields.io/badge/Version-v5.0.8-blue)](https://github.com/Navigaite/nvgt-trunk-plugin/releases)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-June%202025-success)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![Linters](https://img.shields.io/badge/Linters-45%2B-yellow)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![License](https://img.shields.io/badge/License-MIT-green)](./LICENSE)

A centralized configuration plugin for [Trunk](https://trunk.io) that standardizes linting, formatting, and code checking across Navigaite
projects.

## Overview

This plugin provides a unified set of linting rules, configurations, and actions that can be easily shared across multiple repositories
within the Navigaite ecosystem. By sourcing this plugin, repositories automatically inherit our standardized development workflows and
quality controls.

## Features

- **Standardized Linting**: Pre-configured rules for 45+ linters covering multiple languages and frameworks
- **Modern Tooling**: Includes modern tools like `commitlint`, `knip`, and `dependency-cruiser`
- **Shared Configurations**: Centrally managed config files for all major code quality tools
- **Runtime Environments**: Built-in support for Go, Node.js, Python, and Ruby
- **Git Hooks**: Pre-configured hooks for code formatting and quality checks
- **CI/CD Integration**: Ready for CI/CD integration with GitHub Actions workflow examples
- **Security Focus**: Comprehensive security scanning with tools like Semgrep, Bandit, and Trivy

## Supported Languages & Frameworks

The plugin provides standardized configurations for:

- **JavaScript/TypeScript**: ESLint, Prettier, Knip (unused code detection)
- **Python**: Ruff (comprehensive linting), Black (formatting), Pylint, MyPy, Bandit (security)
- **Go**: Gofmt, Golangci-lint
- **Ruby**: Rubocop
- **Rust**: Rustfmt, Clippy
- **Docker**: Hadolint (Dockerfile linting)
- **Infrastructure**: Terraform (Checkov), CloudFormation (CFNLint)
- **Security**: Gitleaks, Semgrep, Trivy, OSV-Scanner
- **Documentation**: Markdownlint, Vale
- **And many more!

## New Tools Added

### Modern Development Tools
- **Commitlint**: Enforce conventional commit message format
- **Knip**: Find unused files, dependencies, and exports in JavaScript/TypeScript projects
- **Dependency Cruiser**: Validate and visualize dependencies

### Enhanced Security
- Comprehensive security scanning with multiple tools
- Dependency vulnerability scanning
- Secret detection in code

## Usage

### Adding to a Repository

1. Install the Trunk CLI following the [official documentation](https://docs.trunk.io)
2. In your repository root, initialize Trunk:
   ```bash
   trunk init
   ```
3. Add this plugin to your `.trunk/trunk.yaml`:
   ```yaml
   plugins:
     sources:
       - id: navigaite
         uri: https://github.com/navigaite/nvgt-trunk-plugin
         ref: v5.0.8 # or main for latest
   ```
4. Run `trunk check` to validate the installation

## Quick Start Examples

### For New Projects
Copy the example configuration from `examples/trunk.yaml` to `.trunk/trunk.yaml` in your repository and adjust as needed.

### For CI/CD Integration
Use the example GitHub Actions workflow from `examples/github-actions-trunk.yml` to set up automated code quality checks.

## Available Configurations

This plugin exports a variety of shared configurations in the `configs/` directory:

- `.commitlintrc.json` - Conventional commit message linting
- `.dependency-cruiser.json` - Dependency validation and visualization
- `knip.json` - Unused code detection for JavaScript/TypeScript
- `.prettierrc` - Formatting rules for JavaScript/TypeScript
- `ruff.toml` - Comprehensive Python linting with Ruff
- `.stylelintrc.json` - CSS/SCSS styling rules with Tailwind support
- `.yamllint.yaml` - YAML linting configuration
- And many more!

## Actions

The following Trunk actions are enabled by default:

- `trunk-check-pre-push` - Run checks before git push
- `trunk-fmt-pre-commit` - Format code before commits
- `trunk-upgrade-available` - Notification for available upgrades
- `trunk-cache-prune` - Automatic cache maintenance

## Maintenance

This plugin includes a GitHub workflow that automatically checks for Trunk updates weekly and creates pull requests as needed.

## Contributing

1. Fork this repository
2. Make your changes
3. Test your changes with `trunk check`
4. Submit a pull request

## License

[MIT](LICENSE)
