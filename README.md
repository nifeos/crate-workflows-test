# crate_workflows_test

[![check](https://github.com/nifeos/crate-workflows-test/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/nifeos/crate-workflows-test/actions/workflows/ci.yml?query=branch%3Amain)
[![proofs](https://github.com/nifeos/crate-workflows-test/actions/workflows/proofs.yml/badge.svg?branch=main)](https://github.com/nifeos/crate-workflows-test/actions/workflows/proofs.yml?query=branch%3Amain)
[![license](https://img.shields.io/badge/license-MIT%20OR%20Apache--2.0-blue.svg)](https://github.com/nifeos/crate-workflows-test#license)
[![minimum Rust version](https://img.shields.io/badge/rust-1.85%2B-blue.svg)](https://github.com/nifeos/crate-workflows-test/blob/main/Cargo.toml)

The throwaway crate repository that proves the template: one function with two tests, one proof,
and a falsification patch. Every shared workflow runs against this repository, from a release tag
of nifeos/crate-workflows, and the repository is deleted after. Its release path is rehearsed with
`dry-run` only; nothing here is published.

## EXAMPLES

```rust
assert_eq!(crate_workflows_test::saturating_add_percent(30, 40), 70);
assert_eq!(crate_workflows_test::saturating_add_percent(60, 60), 100);
```

## BUGS

- The crate proves the workflows, not the function. Nothing here is a claim about percentage
  arithmetic worth depending on.
