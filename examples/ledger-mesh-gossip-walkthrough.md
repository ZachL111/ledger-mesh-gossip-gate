# Ledger Mesh Gossip Gate Walkthrough

This note is the quickest way to read the extra review model in `ledger-mesh-gossip-gate`.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | quorum health | 228 | ship |
| stress | lease drift | 156 | ship |
| edge | replica lag | 139 | watch |
| recovery | membership churn | 233 | ship |
| stale | quorum health | 238 | ship |

Start with `stale` and `edge`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

The next useful expansion would be a malformed fixture around lease drift and membership churn.
