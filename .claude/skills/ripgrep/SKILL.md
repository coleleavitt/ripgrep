```markdown
# ripgrep Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the `ripgrep` Rust codebase, following its coding conventions and established workflows. You'll learn how to structure code, update documentation, manage releases, and handle common maintenance tasks using both manual steps and suggested `/commands`.

## Coding Conventions

### File Naming

- Use **camelCase** for file names.
  - Example: `fileSearch.rs`, `defaultTypes.rs`

### Import Style

- Use **relative imports** within modules.
  - Example:
    ```rust
    use crate::utils::fileSearch;
    ```

### Export Style

- Use **named exports**.
  - Example:
    ```rust
    pub fn search_files(...) { ... }
    ```

### Commit Patterns

- Commit messages are freeform but often use prefixes such as `ignore`, `_rg`, `doc`, `deps`, `docs`, `changelog`, `globset`.
- Example commit: `ignore: add support for .env files`

## Workflows

### Crate Release Version Bump
**Trigger:** When releasing a new version of a crate.  
**Command:** `/release-crate`

1. Update the version number in the crate's `Cargo.toml`.
2. Update `Cargo.lock` to reflect the new version.

**Example:**
```toml
# crates/ignore/Cargo.toml
version = "1.2.3"  # Update this line
```
```bash
cargo update -p ignore
```

### Add New File Type to Ignore Crate
**Trigger:** When supporting a new file type for ignore/filtering.  
**Command:** `/add-file-type`

1. Edit `crates/ignore/src/default_types.rs` to add the new file type.

**Example:**
```rust
// crates/ignore/src/default_types.rs
types.insert("env", Type::new("env", "*.env"));
```

### Documentation Update or Policy Change
**Trigger:** When updating documentation or project policies.  
**Command:** `/update-docs`

1. Edit one or more markdown files such as `CONTRIBUTING.md`, `GUIDE.md`, or `AI_POLICY.md`.

**Example:**
```markdown
# CONTRIBUTING.md

## New Section
Please follow the code style conventions described in SKILL.md.
```

### CI Workflow Update
**Trigger:** When adding new CI targets or updating workflow logic.  
**Command:** `/update-ci`

1. Edit `.github/workflows/ci.yml` and/or `.github/workflows/release.yml`.

**Example:**
```yaml
# .github/workflows/ci.yml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run tests
        run: cargo test
```

### Changelog Update
**Trigger:** When documenting changes or preparing for a release.  
**Command:** `/update-changelog`

1. Edit `CHANGELOG.md` to add or update entries.

**Example:**
```markdown
## [1.2.3] - 2024-06-01
### Added
- Support for `.env` files in ignore crate.
```

## Testing Patterns

- Test files follow the pattern `*.test.ts`.
- The specific testing framework is unknown, but tests are likely colocated or in a `tests/` directory.
- Example test file: `searchFunction.test.ts`

## Commands

| Command            | Purpose                                            |
|--------------------|---------------------------------------------------|
| /release-crate     | Bump crate version and update lockfile            |
| /add-file-type     | Add a new file type to the ignore crate           |
| /update-docs       | Update documentation or contributor policies      |
| /update-ci         | Update CI or release workflow configuration       |
| /update-changelog  | Add or update entries in the changelog            |
```