# Data Dictionary — Legal Analytics Dimensional Model

## Overview

This data dictionary describes the dimensional model used by the Legal Analytics platform. The model follows a star schema and is centered on the Fact_Resource fact table, which stores information about judicial resources and connects them to descriptive dimensions such as process, class, organization, degree, result, time, and subject.

## 1. Fact Tables

### Fact_Resource

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_resource` | Integer | PK | Unique identifier of the judicial resource. |
| `id_time` | Integer | FK | Reference to the time dimension. |
| `id_class` | Integer | FK | Reference to the procedural class. |
| `id_org` | Integer | FK | Reference to the judicial organization. |
| `id_degree` | Integer | FK | Reference to the judicial degree or instance. |
| `id_result` | Integer | FK | Reference to the resource result. |
| `id_process` | Integer | FK | Reference to the related judicial process. |
| `quant_resource` | Integer | — | Quantity of resources represented by the record. |

### Fact_Process_Subject

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_subject` | Integer | PK, FK | Reference to the legal subject. |
| `id_process` | Integer | PK, FK | Reference to the judicial process. |
| `id_resource` | Integer | PK, FK | Reference to the judicial resource. |
| `id_class` | Integer | FK | Reference to the procedural class. |
| `id_org` | Integer | FK | Reference to the judicial organization. |
| `id_result` | Integer | FK | Reference to the result. |
| `id_degree` | Integer | FK | Reference to the judicial degree or instance. |
| `id_time` | Integer | FK | Reference to the time dimension. |

---

# 2. Dimension Tables

### DIM_Process

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_process` | Integer | PK | Unique identifier of the judicial process. |
| `number_process` | Char(20) | — | Official identification number of the judicial process. |
| `secrecy_level` | Integer | — | Confidentiality or secrecy level of the process. |

### DIM_Class

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_class` | Integer | PK | Unique identifier of the procedural class. |
| `code_cls` | Integer | — | Official code of the procedural class. |
| `name_cla` | Varchar(100) | — | Name or description of the procedural class. |

### DIM_Org

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_org` | Integer | PK | Unique identifier of the judicial organization. |
| `code_org` | Integer | — | Official code of the judicial organization. |
| `name_org` | Varchar(100) | — | Name of the judicial organization. |
| `IBGE_code` | Integer | — | IBGE code associated with the organization. |

### DIM_Degree

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_degree` | Integer | PK | Unique identifier of the judicial degree. |
| `code_degree` | Varchar(50) | — | Code representing the judicial degree or instance. |
| `name_degree` | Varchar(100) | — | Name or description of the judicial degree. |

### DIM_Time

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_time` | Integer | PK | Unique identifier of the date record. |
| `date` | Date | — | Calendar date associated with the record. |
| `year` | Integer | — | Year of the corresponding date. |
| `month` | Integer | — | Month of the corresponding date. |
| `day` | Integer | — | Day of the corresponding date. |
| `quarter` | Integer | — | Quarter of the corresponding date. |

### DIM_Result

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_result` | Integer | PK | Unique identifier of the result. |
| `name_result` | Varchar(20) | — | Name or classification of the judicial result. |

### DIM_Subject

| Column | Data Type | Key | Description |
|---|---|---|---|
| `id_subject` | Integer | PK | Unique identifier of the legal subject. |
| `code_subject` | Integer | — | Official code representing the legal subject. |
| `name_subject` | Varchar(100) | — | Name or description of the legal subject. |

---

# 3. Relationships

| Source | Relationship | Target | Description |
|---|---|---|---|
| `Fact_Resource.id_time` | N:1 | `DIM_Time.id_time` | Associates a resource with a date. |
| `Fact_Resource.id_class` | N:1 | `DIM_Class.id_class` | Associates a resource with a procedural class. |
| `Fact_Resource.id_org` | N:1 | `DIM_Org.id_org` | Associates a resource with a judicial organization. |
| `Fact_Resource.id_degree` | N:1 | `DIM_Degree.id_degree` | Associates a resource with a judicial degree. |
| `Fact_Resource.id_result` | N:1 | `DIM_Result.id_result` | Associates a resource with its result. |
| `Fact_Resource.id_process` | N:1 | `DIM_Process.id_process` | Associates a resource with a judicial process. |
| `Fact_Process_Subject.id_subject` | N:1 | `DIM_Subject.id_subject` | Associates a process/resource with a legal subject. |
| `Fact_Process_Subject.id_process` | N:1 | `DIM_Process.id_process` | Associates the subject with a judicial process. |
| `Fact_Process_Subject.id_resource` | N:1 | `Fact_Resource.id_resource` | Associates the subject with a judicial resource. |
| `Fact_Process_Subject.id_class` | N:1 | `DIM_Class.id_class` | Associates the subject with a procedural class. |
| `Fact_Process_Subject.id_org` | N:1 | `DIM_Org.id_org` | Associates the subject with a judicial organization. |
| `Fact_Process_Subject.id_result` | N:1 | `DIM_Result.id_result` | Associates the subject with a result. |
| `Fact_Process_Subject.id_degree` | N:1 | `DIM_Degree.id_degree` | Associates the subject with a judicial degree. |
| `Fact_Process_Subject.id_time` | N:1 | `DIM_Time.id_time` | Associates the subject with a date. |

The Fact_Resource table is the main analytical fact, allowing the dashboard to analyze judicial resources by time, procedural class, organization, degree, result, and process. Fact_Process_Subject provides the additional relationship between resources/processes and their legal subjects, supporting subject-based analysis.