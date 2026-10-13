# Detailed Analysis – Report Support

Use this file as a working analysis appendix. The individual Task_1 through Task_12 folders contain the task-specific write-ups.

## Mathematical summary
- Linear search: best Θ(1), average successful Θ(n), worst Θ(n), no preprocessing.
- Binary search: best Θ(1), average/worst Θ(log n) on sorted data; sorting costs O(n log n).
- Hash table: expected construction Θ(n), expected lookup Θ(1), worst-case lookup Θ(n), extra space Θ(n).

## Workload analysis
50,000 searches/hour is about 13.89 searches/second on average. With one million records, a worst-case linear scan could perform 50 billion record comparisons per hour. This is an operation-count upper scenario, not an elapsed-time measurement. A real deployment needs concurrent load tests, latency percentiles, memory monitoring and database/index consistency tests.

## Experimental report checklist
- [ ] Record Python version and system specifications.
- [ ] Run all four dataset sizes.
- [ ] Confirm every `correct` value is true.
- [ ] Review CSV and graphs.
- [ ] Insert actual measured values and discuss them.
- [ ] Capture screenshots from the real run.
- [ ] Export the final report to PDF.
