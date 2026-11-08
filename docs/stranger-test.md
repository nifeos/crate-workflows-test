# The stranger cadence

The release's whole claim is that a stranger, given this repository and nothing else, can build
the crate and run its proofs from the README alone. The organization runs that check with a real agent on a
cadence; this crate owes the same ritual, and the weekly `stranger cadence` job fails when the
last run is past 28 days.

What a run is:

1. Clone the repository fresh.
2. Follow the README and nothing else: build, test, and run the proofs.
3. Note every place the README lied, omitted, or assumed. Those are findings against the README,
   not against the stranger.
4. Record the date on the line below.

Last run: 2026-11-08

## What the last run did

A fresh clone and the README, on a machine that already had Rust and Kani.

- `cargo build` and `cargo test` pass: 2 unit tests and 1 documentation test.
- `cargo kani` verifies the one harness, `proofs::saturating_add_percent_capped`.
- `patch -p1 < falsifications/src.proofs.saturating_add_percent_capped.patch`, then `cargo kani`,
  fails the harness at its own assertion. `git checkout -- .` undoes the patch and leaves the tree
  clean.

The README gives no build, test or proof command, does not name Kani or the Rust version as
prerequisites, and does not say where the falsification patch is or how to apply and undo it. The
stranger used the usual Cargo and Kani commands and found the patch by listing the tree. This
crate exists to exercise the shared workflows, so the README stays short and these gaps stay
open. Result: pass, with those four gaps.
