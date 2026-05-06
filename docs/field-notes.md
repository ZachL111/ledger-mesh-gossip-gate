# Field Notes

This note keeps the distributed systems assumptions visible beside the checks.

The domain cases cover `quorum health`, `lease drift`, `replica lag`, and `membership churn`. They sit beside the smaller starter fixture so the project has both a compact scoring check and a domain-flavored review check.

`stale` is the strongest case at 238 on `quorum health`. `edge` is the cautious anchor at 139 on `replica lag`.

The local verifier covers this data so the notes stay tied to code.
