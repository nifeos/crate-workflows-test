# crate_workflows_test

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
