---
name: add-new-file-type-to-ignore-crate
description: Workflow command scaffold for add-new-file-type-to-ignore-crate in ripgrep.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-file-type-to-ignore-crate

Use this workflow when working on **add-new-file-type-to-ignore-crate** in `ripgrep`.

## Goal

Add support for a new file type in the ignore crate for filtering purposes.

## Common Files

- `crates/ignore/src/default_types.rs`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit crates/ignore/src/default_types.rs to add the new file type.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.