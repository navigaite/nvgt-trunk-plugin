# Navigaite Trunk Plugin

[![Trunk](https://img.shields.io/badge/Trunk-Powered-brightgreen)](https://trunk.io)
[![Version](https://img.shields.io/badge/Version-0.1-blue)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-May%202025-success)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![Languages](https://img.shields.io/badge/Languages-40%2B-orange)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![Linters](https://img.shields.io/badge/Linters-40%2B-yellow)](https://github.com/Navigaite/nvgt-trunk-plugin)
[![License](https://img.shields.io/badge/License-MIT-green)](./LICENSE)

A centralized configuration plugin for [Trunk](https://trunk.io) that standardizes linting, formatting, and code checking across Navigaite
projects.

## Overview

This plugin provides a unified set of linting rules, configurations, and actions that can be easily shared across multiple repositories
within the Navigaite ecosystem. By sourcing this plugin, repositories automatically inherit our standardized development workflows and
quality controls.

## Features

- **Standardized Linting**: Pre-configured rules for 40+ linters covering multiple languages and frameworks
- **Shared Configurations**: Centrally managed config files for all major code quality tools
- **Runtime Environments**: Built-in support for Go, Node.js, Python, and Ruby
- **Git Hooks**: Pre-configured hooks for code formatting and quality checks
- **CI/CD Integration**: Ready for CI/CD integration with GitHub Actions workflow examples

## Supported Languages & Frameworks

The plugin provides standardized configurations for:

- JavaScript/TypeScript (ESLint, Prettier)
- Python (Ruff, Black, Pylint, MyPy)
- Go (Gofmt, Golangci-lint)
- Ruby (Rubocop)
- Rust (Rustfmt, Clippy)
- And many more!

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
         uri: git@github.com:Navigaite/nvgt-trunk-plugin.git
         ref: main # or specific version tag
   ```
4. Run `trunk check` to validate the installation

## Available Configurations

This plugin exports a variety of shared configurations in the `configs/` directory:

- `.prettierrc` - Formatting rules for JavaScript/TypeScript
- `ruff.toml` - Python linting with Ruff
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
