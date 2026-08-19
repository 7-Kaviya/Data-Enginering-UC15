# Project Charter
### Enterprise Resource Planning Data Platform (ERPDP)

## Objective
Build a unified data platform that consolidates ABC Global Enterprises Ltd.'s ERP data from multiple modules into a trusted PostgreSQL warehouse, enabling consistent enterprise-wide reporting and analytics.

## Scope
**In:** Ingest data from multiple ERP modules (CSV, Excel, JSON, XML, SQL) into PostgreSQL staging, clean and profile it, build a star-schema warehouse, and produce executive dashboards.

**Out:** Real-time streaming, replacing the existing ERP, mobile apps. Sample/academic data is used in place of a live ERP connection.


## Timeline

| Sprint | Focus | DA |
|---|---|---|
| 0 | Project Initiation & Architecture | DA1 |
| 1 | Data Discovery & Ingestion | DA1 |
| 2 | Data Profiling & Warehouse | DA2 |
| 3 | Governance, Lineage & Analytics | DA3 |

## Success Criteria
- All ERP modules ingested into PostgreSQL staging with a full audit trail
- Data dictionary and source inventory fully documented
- Traceable, incremental commit history in the shared Git repository

