---
name: crate-release-version-bump
description: Workflow command scaffold for crate-release-version-bump in ripgrep.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /crate-release-version-bump

Use this workflow when working on **crate-release-version-bump** in `ripgrep`.

## Goal

Release a new version of a crate by updating its Cargo.toml and Cargo.lock.

## Common Files

- `Cargo.lock`
- `crates/*/Cargo.toml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update the version number in the crate's Cargo.toml.
- Update Cargo.lock to reflect the new version.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.