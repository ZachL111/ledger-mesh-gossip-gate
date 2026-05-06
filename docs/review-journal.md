# Review Journal

The repository goal stays the same: implement an SQL distributed systems project for gossip event replay, using fixture event logs and golden state snapshots. This note explains the added review angle.

The local checks classify each case as `ship`, `watch`, or `hold`. That gives the project a small review vocabulary that matches its distributed systems focus without claiming live deployment or external usage.

## Cases

- `baseline`: `quorum health`, score 228, lane `ship`
- `stress`: `lease drift`, score 156, lane `ship`
- `edge`: `replica lag`, score 139, lane `watch`
- `recovery`: `membership churn`, score 233, lane `ship`
- `stale`: `quorum health`, score 238, lane `ship`

## Note

A future change should add new cases before it changes the scoring rule.
