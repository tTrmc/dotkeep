# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> **Note**: This project was renamed from "dotkeep" to "dotz" starting with version 0.4.0.
> Historical entries below may reference the old "dotkeep" command name.

## [Unreleased]

- Future features will be listed here

## [0.4.0] - 2025-07-12

### Major release with GUI interface and comprehensive development automation

### Added

- **Qt6/PySide6 Graphical User Interface**
  - Modern tabbed interface with dashboard, file management, and settings
  - Visual file browser with add/remove capabilities
  - Interactive repository setup wizard
  - Real-time status monitoring and progress indicators

- **Advanced Git Integration**
  - `dotz commit` - Create commits with descriptive messages
  - `dotz diff` - View changes between working directory and repository
  - Enhanced Git operations with better error handling

- **Comprehensive Development Automation**
  - Pre-commit hooks with Python-only toolchain (black, isort, flake8, mypy, bandit)
  - Conventional commit message enforcement
  - Automated code quality checks and security scanning
  - Enhanced CI/CD pipeline with pre-commit validation

- **Enhanced Documentation & Developer Experience**
  - Complete PRE_COMMIT.md setup guide
  - Updated CONTRIBUTING.md with automation workflow
  - Enhanced Makefile with setup, security, and docs targets
  - Streamlined setup-dev.sh with virtual environment validation

### Changed

- **BREAKING**: Project renamed from "dotkeep" to "dotz"
  - Command changed from `dotkeep` to `dotz`
  - Configuration directory changed from `~/.dotkeep` to `~/.dotz`
  - Package name changed from `dotkeepctl` to `dotz`

- **Enhanced Project Branding**
  - Updated description from "minimal" to "fully featured"
  - Improved README with comprehensive feature descriptions
  - Enhanced GitHub issue templates and workflows

- **Development Workflow Improvements**
  - Consolidated tool configurations for consistency
  - Removed Node.js dependencies (Python-only development)
  - Enhanced CI with comprehensive linting and security checks

### Fixed

- Security issues in core.py with proper tar extraction validation
- Improved exception handling patterns
- Enhanced virtual environment setup and activation
- Better error messages and user guidance

### Technical Improvements

- Modern Qt6-based GUI architecture
- Enhanced type checking and code quality standards
- Comprehensive pre-commit automation infrastructure
- Improved development environment setup and documentation

## [0.3.0] - 2025-07-05

### Professional release with comprehensive improvements and modern packaging

### Added

- Comprehensive test suite with 73+ passing tests
- Environment isolation for robust testing
- Configuration management system with `dotkeep config` commands
- File pattern customization (include/exclude patterns)
- Search settings configuration (recursive, case-sensitive, follow-symlinks)
- Improved error handling and diagnostics
- Modern Python packaging with `pyproject.toml`
- GitHub Actions CI/CD pipeline
- Professional documentation (CONTRIBUTING.md, PUBLISHING.md)
- Development tooling (Makefile, setup-dev.sh)

### Changed

- Refactored path management for better testability
- Updated license field in pyproject.toml to modern SPDX string format
- Enhanced fixtures for test isolation
- Improved documentation with configuration examples
- Professional CLI output (removed unprofessional emojis, kept ✓ marks)
- Complete rewrite for robustness and maintainability

### Fixed

- Test pollution issues between test runs
- Path resolution in different environments
- Configuration persistence and cleanup

## [0.2.0] - 2025-07-05

### Highlights

#### **Recursive Directory Support**

- Add all dotfiles in a directory and its subdirectories with `dotkeep add <dir>`
- Use `--no-recursive` to restrict to top-level dotfiles only

#### **Tracked Directories & Watcher**

- Only explicitly added directories are monitored for new dotfiles
- `dotkeep watch` automatically adds new dotfiles created in tracked directories

#### **Diagnostics**

- New `dotkeep diagnose` command checks for common setup and git issues, providing actionable guidance

#### **Enhanced Git Integration**

- Improved error messages for common git issues (e.g., divergent branches, missing upstream, rejected pushes)
- Upstream branch is set automatically on first push if needed

#### **Improved CLI Experience**

- `--quiet` flag suppresses output for scripting and automation
- `--push` flag available for `add`, `delete`, and `restore` to immediately push changes
- `dotkeep version` displays the current version
- `dotkeep --install-completion` enables shell tab-completion for all commands and options

#### **Commit Efficiency**

- Adding multiple dotfiles in a directory now results in a single commit, improving repository clarity

### Improvements & Fixes

- Robust handling of symlinks and prevention of watcher loops
- Tracked directories are automatically removed from tracking when all dotfiles inside are deleted
- Consistent, user-friendly CLI output
- Expanded and improved test suite for CLI and core logic

### Requirements

- Python 3.8+
- Git

### Installation

```bash
git clone https://github.com/tTrmc/dotkeep.git
cd dotkeep
pip install -e .
```

### Getting Started

```bash
dotkeep init
dotkeep add .bashrc
dotkeep status
dotkeep push
```

See the README for full usage instructions and advanced features.

## [0.1.0] - First Public Release

### dotkeep is a minimal, Git-backed dotfiles manager for Linux

This is the first public release.

### Features

- **Easy setup:**
  Initialize your dotfiles repo with `dotkeep init`.
  The Git repository is stored in `~/.dotkeep/repo`.

- **Git-based versioning:**
  All changes are tracked with Git.
  Supports local history, branching, and remote sync.

- **Add and remove dotfiles:**
  - `dotkeep add <file>`: Copies a file into the repo, commits it, and symlinks it from your home directory.
  - `dotkeep delete <file>`: Removes the symlink and the file from the repo and Git.

- **Symlink management:**
  Automatically replaces managed files in `$HOME` with symlinks to the repo.

- **Status overview:**
  `dotkeep status` shows untracked, modified, and staged files in your dotkeep repo.

- **Remote sync:**
  - `dotkeep push`: Push all local commits to your remote.
  - `dotkeep pull`: Pull and merge changes from your remote.

- **Restore files:**
  `dotkeep restore <file>`: Re-create the symlink for a managed file if it's missing.

- **List tracked files:**
  `dotkeep list-files`: See all files currently managed by dotkeep.

### Requirements (v0.1.0)

- Python 3.8+
- Git

### Installation (v0.1.0)

```bash
git clone https://github.com/tTrmc/dotkeep.git
cd dotkeep
pip install -e .
```

### Getting Started (v0.1.0)

```bash
dotkeep init
dotkeep add .bashrc
dotkeep status
dotkeep push
```

See the README for full usage instructions.
