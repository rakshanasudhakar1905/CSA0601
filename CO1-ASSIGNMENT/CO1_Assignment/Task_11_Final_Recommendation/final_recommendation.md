# Task 11 – Final Design Recommendation

## Candidate recommendation
For repeated exact-match lookup by a unique registration number, a hash-based index is a strong candidate because lookup is expected Θ(1) after expected Θ(n) construction. A database's persistent unique index is generally more suitable for a real university service than rebuilding an in-memory Python dictionary for every application start.

## Alternatives and trade-offs
- Linear search: minimal setup, but Θ(n) per lookup; appropriate mainly for tiny collections or rare queries.
- Binary search: Θ(log n) lookup after sorting; good when sorted order and range queries matter, but sorting is O(n log n) if needed.
- Hash table: expected Θ(1) exact lookup and expected Θ(n) construction, but requires memory and has Θ(n) pathological worst-case lookup.

## Evidence required
Insert measured timings from the benchmark. State the machine/Python environment, include preprocessing cost, and explain why the chosen structure suits the measured workload. Do not select an algorithm based on Big-O alone.
