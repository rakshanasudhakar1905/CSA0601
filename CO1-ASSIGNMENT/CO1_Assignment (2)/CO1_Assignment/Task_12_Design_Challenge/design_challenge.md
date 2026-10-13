# Task 12 – Day-4 Design Challenge (8 Marks)

## A. Impact analysis (2 marks)
The revised workload has 1,000,000 records, 50,000 search requests per hour, and new records added once per day. The average arrival rate is 50,000 / 3,600 ≈ 13.89 requests/second; peak load may be higher. Frequent reads and relatively infrequent writes make one-time index construction and incremental daily updates attractive.

## B. Evaluate original design (2 marks)
Linear search may require up to 1,000,000 comparisons per query. At 50,000 queries/hour, that is up to 50 billion record comparisons/hour in a worst-case scan-count estimate, not a measured runtime. Binary search requires about log₂(1,000,000) ≈ 20 midpoint levels after sorting. Hash lookup is expected O(1) with suitable hashing, at the cost of index memory and construction.

## C. Adaptation/redesign (2 marks)
**Decision: modify the design to use a persistent indexed database lookup.** Use a unique index on the registration-number field; for a prototype, a dictionary/hash index models expected constant-time exact lookups. Update the index transactionally when new records are inserted daily. A database-managed index supports persistence, concurrency, recovery and consistency better than rebuilding an in-memory structure for each query.

Complexities: hash-index construction is expected O(n), exact lookup expected O(1), insertion expected O(1) for the hash operation (with occasional resize/collision costs). A database B-tree index commonly gives O(log n) lookup and insertion and may be preferable where durability, range queries and database integration matter.

## D. Evidence-based defence (2 marks)
Insert actual one-million-record measurements from the benchmark and compare search time plus preprocessing. Discuss memory, concurrency, daily update cost and peak traffic. Average load is about 13.89 searches/second, but validate the production system using a realistic concurrent load test. A local Python benchmark alone does not prove production capacity.

## Final position
Recommend a persistent database index for production exact-match queries, with a hash-table prototype as the experimental candidate. This balances expected lookup speed with data durability and operational needs. The final defence must reference measured results from the student's own run.
