# Terms
* CDC: Capture changes in the source and delivering to the target
* CDF: Change data feed
	* Auto records data changes in Delta tables
	* Retrive: Select * from table_changes(name, start_version/timestamp, [end/version/timestamp])
	* Schema

| Col1 | Col2 | ... | Change Type      | Time     | Version |
| ---- | ---- | --- | ---------------- | -------- | ------- |
| Val1 | Val2 | ... | update_preimage  | 00:00:01 | 2       |
| Val1 | Val3 | ... | update_postimage | 00:00:02 | 2       |

# Q&A
1. Can we use Delta Time Travel as SCD Type 2? -> NO
	* Do not scale well in cost and latency
	- Run vacuum deleted
2. What is merge limitation
* Multiple source rows matched
- Attempted to modify same target row
- CDC with multiple updates for the same key

Non-time-based windows is not supported on streaming DF

# Change Data Feed

