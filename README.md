Deployment Simplicity
----------------------

1. Uses native Azure services: Cosmos DB, Blob Storage, Table Storage, Azure Functions.
2. No third-party tools or changes to API interface.
3. Easy to monitor and scale using Azure Monitor and Function scaling rules.

Cost Impact
------------

| Component                           | Storage Cost            | Access Cost                |
| ----------------------------------- | ----------------------- | -------------------------- |
| Cosmos DB                           | Reduced (only 3 months) | Very low                   |
| Blob Storage (Cool or Archive Tier) | Extremely low           | Small latency (acceptable) |
| Table Storage (Index)               | Minimal                 | Very low                   |



Solution Overview
------------------

* Trigger: Timer (runs daily or weekly)
* Reads: Cosmos DB (records > 90 days old)
* Writes: Azure Blob Storage (JSON) + Azure Table Storage (index)
* Deletes: Records from Cosmos DB
