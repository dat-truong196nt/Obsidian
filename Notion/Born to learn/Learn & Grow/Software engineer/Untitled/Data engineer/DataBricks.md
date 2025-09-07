---
sticker: lucide//database
banner: "Notion/System/Images/databricks.webp"
---
# Terms
* CDC
	* Change data capture
	* Capture changes in the source and delivering to the target
* CDF: Change data feed
	* delta.enableChangeDataFeed = true
	* Auto records data changes in Delta tables
	* Retrive: Select * from table_changes(name, start_version/timestamp, [end/version/timestamp])
	* Schema
* Window function
	* FUNCTION() OVER(WINDOW)
		* FUNCTION(): What to do?
		* WINDOW: How your data should look like?
	* Examples:
		* ROW_NUMBER() OVER(ORDER BY col DESC)
		* RANK() OVER(PARTITION BY col1 ORDER BY col2 DESC)
	* Ref: https://www.youtube.com/watch?v=rIcB4zMYMas&t=460s

| Col1 | Col2 | ... | Change Type      | Time     | Version |
| ---- | ---- | --- | ---------------- | -------- | ------- |
| Val1 | Val2 | ... | update_preimage  | 00:00:01 | 2       |
| Val1 | Val3 | ... | update_postimage | 00:00:02 | 2       |
| Val2 | Val3 | ... | insert           | 00:00:02 | 2       |

# Q&A
1. Can we use Delta Time Travel as SCD Type 2? -> NO
	* Do not scale well in cost and latency
	- Run vacuum deleted
2. What is merge limitation
	* Multiple source rows matched
	- Attempted to modify same target row
	- CDC with multiple updates for the same key
3. Stream-Static join
	* Each micro batch will fetch the latest version of static table

Non-time-based windows is not supported on streaming DF

# Change Data Feed
# View
* Nothing from SQL query against tables
* Compute results on demand
	* Each time query the view -> Execute table again -> Costly
## Materialize view
* Cache and update as source change (Schedule/Auto)
# Performance optimization

## Data File Layout
### Partitioning
* Large tables only
* Optimize query performance by partitioning (select/delete)
* Choosing a partition
	* Low cardinality fields
	* Each partition > 1Gb
* Delete data break append-only requirement in streaming.
* Delete will not actually occur until run VACUUM (data file only)
### Z-Order Indexing
* Small tables
* Need rewrite all data when new data come.
* Collocate value in columns that commonly used in query.
### Liquid Clustering
* Auto analyze and group data
## Deltalake transaction log
### Log checkpoint
* Each commit create a .json log
	* Statistics
		* Total # of records
		* First 32 columns (Min, Max, NullCount)
* Move high cardinality out of first 32 columns.
* 10 commits create a .parquet checkpoint
* Auto delete log for each commit (>retetion)
# Tooling
## 
