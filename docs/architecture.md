# High-Level Solution Architecture
### ERPDP — ABC Global Enterprises Ltd.

## Overview
Data flows in one direction, left to right, from raw ERP source files through to reporting. Each layer only talks to the one next to it, which keeps the system easy to debug and extend.

## Layers

**1. ERP Source Files**
Raw exports from the multiple ERP modules (Finance, Procurement, Sales, Inventory, Manufacturing, HR, Warehouse, Asset Management, Vendor/Customer Master), in CSV, Excel, JSON, XML, or SQL format.

**2. Pentaho ETL (Spoon)**
Reads each source format using a dedicated transformation per source. Handles basic error logging and routes failed records separately, without transforming the data's meaning just moving it.

**3. PostgreSQL Staging**
Raw data lands here almost exactly as it came from the source, plus audit columns (`load_timestamp`, `source_file`). This preserves an unmodified copy for traceability before any cleaning happens.

**4. Star Schema Warehouse**
Staged data will later be cleaned, deduplicated, and restructured into fact and dimension tables optimized for reporting.

**5. Reporting**
Power BI and SQL queries will read from the warehouse to produce executive dashboards.

## Cross-cutting: Git
Every layer's code and documentation — Pentaho transformations, SQL scripts, docs — is version-controlled in Git, giving a full audit trail of who changed what and when.

