# ledger-mesh-gossip-gate

`ledger-mesh-gossip-gate` is a compact SQL repository for distributed systems, centered on this goal: Implement an SQL distributed systems project for gossip event replay, using fixture event logs and golden state snapshots.

## Why I Keep It Small

I want this repository to be useful as a quick reading exercise: fixtures first, implementation second, verifier last.

## Ledger Mesh Gossip Gate Review Notes

The first comparison I would make is `quorum health` against `replica lag` because it shows where the rule is most opinionated.

## Included Behavior

- `fixtures/domain_review.csv` adds cases for quorum health and lease drift.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/ledger-mesh-gossip-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `quorum health` and `replica lag`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Internal Model

The implementation keeps the scoring rule plain: reward signal and confidence, preserve slack, penalize drag, then classify the result into a review lane.

The SQL checks add a separate view over the domain review fixture.

## Try It Locally

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Validation

The same command runs the local verification path. The highest-scoring domain case is `stale` at 238, which lands in `ship`. The most cautious case is `edge` at 139, which lands in `watch`.

## Scope

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
