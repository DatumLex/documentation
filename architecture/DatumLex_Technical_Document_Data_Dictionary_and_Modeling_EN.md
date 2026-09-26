# 📖 Technical Document – Data Dictionary and Modeling

**Project:** DatumLex – Sprint 1  
**Scope:** TJDFT, Civil Liability, records from 2023 onward; DataJud as the sole data source.  
**Database:** PostgreSQL

## 1. Introduction

This document consolidates the definitions of data, tables, fields, and relationships within the Data Warehouse. It ensures that the implementation is unambiguous and can be validated by the team.

## 2. Modeling Artifacts

- **Conceptual:** Main entities (Case, Class, Organization, Result, Subject, Time).
- **Logical:** Relationships between dimensions and facts.
- **Physical:** SQL script (Redgate / Django migrations).
- **Dictionary:** Detailed definitions for each table and field.

## 3. Data Dictionary

### 3.1 Dimension Tables

| Table | Field | Type / Size | Nullability | PK/FK | Business Description |
|---|---|---|---|---|---|
| DIM_Class | id_class | INT | NOT NULL | PK | Process class identifier |
| | code_class | INT | NOT NULL | | Process class code |
| | name_class | VARCHAR(100) | NOT NULL | | Process class name |
| DIM_Degree | id_degree | INT | NOT NULL | PK | Jurisdiction level identifier |
| | code_degree | VARCHAR(50) | NOT NULL | | Jurisdiction level code |
| | name_degree | VARCHAR(100) | NOT NULL | | Jurisdiction level name |
| DIM_Org | id_org | INT | NOT NULL | PK | Judicial body identifier |
| | code_org | INT | NOT NULL | | Judicial body code |
| | name_org | VARCHAR(100) | NOT NULL | | Judicial body name |
| | IBGE_code | INT | NOT NULL | | IBGE locality code |
| DIM_Process | id_process | INT | NOT NULL | PK | Process identifier |
| | number_process | CHAR(20) | NOT NULL | | Unique process number |
| | secrecy_level | INT | NOT NULL | | Process confidentiality level |
| DIM_Result | id_result | INT | NOT NULL | PK | Result identifier |
| | name_result | VARCHAR(20) | NOT NULL | | Result name |
| DIM_Subject | id_subject | INT | NOT NULL | PK | Subject identifier |
| | code_subject | INT | NOT NULL | | Subject code |
| | name_subject | VARCHAR(100) | NOT NULL | | Subject name |
| DIM_Time | id_time | INT | NOT NULL | PK | Time identifier |
| | data | DATE | NOT NULL | | Complete date |
| | year | INT | NOT NULL | | Year |
| | month | INT | NOT NULL | | Month |
| | day | INT | NOT NULL | | Day |
| | quarter | INT | NOT NULL | | Quarter |

### 3.2 Fact Tables

| Table | Main Fields | Primary Key | Foreign Keys | Description |
|---|---|---|---|---|
| Fact_Resource | id_resource, id_class, id_process, id_org, id_degree, id_time, id_result, quant_resource | Composite PK | FKs to all dimensions | Represents procedural resources |
| Fact_Process_Subject | id_resource, id_class, id_process, id_org, id_degree, id_time, id_result, id_subject | Composite PK | FKs to all dimensions + DIM_Subject | Relates processes to their subjects |

## 4. Relationships

- **Fact_Resource** → DIM_Class, DIM_Degree, DIM_Org, DIM_Process, DIM_Result, DIM_Time
- **Fact_Process_Subject** → all previous dimensions + DIM_Subject

## 5. Source and Transformations

- **Source:** DataJud.
- **Transformations:** name normalization, process deduplication, result categorization.
- **Domains:** process classes, jurisdiction levels, judicial bodies, subjects, results.
- **Metrics:** resource count, dismissal rate, temporal distribution.

## 6. Versioning and Evidence

- Document versioned in Git.
- Pull requests with reviews.
- Evidence: query screenshots (`SELECT * FROM dim_org`), load logs in Railway.
