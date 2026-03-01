# Changelog

## [6.0.0] - 2026-03-01

### Breaking Changes

- **python**: Removed black, isort, pylint, bandit, and flake8 in favor of ruff (covers all their functionality)
- **python**: Bumped ruff target-version from py38 to py310 (Python 3.8 is EOL)
- **security**: Removed gitleaks (trufflehog provides superset of functionality)
- **configs**: Removed `.flake8`, `.isort.cfg`, `.pylintrc` (replaced by `ruff.toml`)

### Features

- **ci**: Added universal pipeline integration (`ci.yaml` + `.github/pipeline.yaml`)
- **ci**: Added weekly automated release workflow with categorized changelogs
- **ci**: Added nightly maintenance workflow (cleanup, security audit, dependency check)
- **ci**: Added Dependabot configuration for GitHub Actions and npm dependencies
- **configs**: Added biome.json, knip.json, .commitlintrc.json, .dependency-cruiser.json to exported configs
- **docs**: Improved README with tables for tools, configs, actions, workflows, and runtimes

### Bug Fixes

- **configs**: Fixed corrupted `.prettierrc` keys (`consolejsxSingleQuoteconsole` etc.)
- **configs**: Aligned Biome and Prettier formatting settings (single quotes, 120 char width, trailing commas)
- **plugin**: Fixed incomplete comment and typo in plugin.yaml header
- **plugin**: Bumped `required_trunk_version` from 1.6.8 to 1.22.0

### Changed

- **runtimes**: Bumped Go from 1.21.7 to 1.23.6, Python from 3.12.2 to 3.13.3
- **configs**: Updated Biome schema from 1.9.4 to 2.0.0
- **configs**: Updated Prettier `printWidth` from 140 to 120 (consistent with Biome)
- **ci**: Migrated from `tibdex/github-app-token` to `actions/create-github-app-token`
- **ci**: Replaced manual release workflow with universal pipeline + weekly release
- **plugin**: Reorganized linter list by category with section comments
- **examples**: Updated to reflect universal pipeline pattern and current versions

## [5.0.8] - 2025-06-30

### Added

- Enhanced configuration management and version consistency
- Improved documentation and examples

### Changed

- Updated version badges and documentation timestamps
- Refined linter configurations for better performance

## [4.1.0](https://github.com/navigaite/nvgt-trunk-plugin/compare/v4.0.0...v4.1.0) (2025-05-07)

### Features

- **workflow:** add tagging for major and minor versions
  ([c0dbf23](https://github.com/navigaite/nvgt-trunk-plugin/commit/c0dbf230527c69719e1551a9f8d7138104246861))

### Bug Fixes

- **workflow:** change pull-requests permission to write
  ([59c5467](https://github.com/navigaite/nvgt-trunk-plugin/commit/59c546761f8a29e71eb3cd86c0dfd629dead93cf))
- **workflow:** correct token usage for release-please-action
  ([1ad7fb0](https://github.com/navigaite/nvgt-trunk-plugin/commit/1ad7fb0e6a638c62865477ba472ba1b5f3d2e0af))
- **workflow:** update release-please-action usage and token handling
  ([c0dbf23](https://github.com/navigaite/nvgt-trunk-plugin/commit/c0dbf230527c69719e1551a9f8d7138104246861))
