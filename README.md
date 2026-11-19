# Data Warehouse and Analytics Project

[![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://www.microsoft.com/en-us/sql-server)
[![T-SQL](https://img.shields.io/badge/T--SQL-4479A1?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://learn.microsoft.com/en-us/sql/t-sql/)
[![Architecture](https://img.shields.io/badge/Architecture-Medallion-blue?style=for-the-badge)](#data-architecture)
[![Git](https://img.shields.io/badge/Version%20Control-Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

## 1. Project Overview

The **Data Warehouse and Analytics Project** focuses on designing and implementing a centralized data warehouse using Microsoft SQL Server. The solution integrates structured data from Enterprise Resource Planning (ERP) and Customer Relationship Management (CRM) source systems to establish a unified and reliable foundation for business intelligence and analytical reporting.

The implementation follows the Medallion Architecture, comprising Bronze, Silver, and Gold data layers. Each layer represents a distinct stage of the data processing lifecycle, from raw data ingestion to data cleansing, integration, and analytical modeling.

The project demonstrates practical Data Engineering capabilities, including database development, ETL pipeline implementation, data transformation, data quality validation, dimensional modeling, and SQL-based business analytics.

## 2. Project Objectives

The primary objectives are to:

- Design and implement a structured data warehouse using Microsoft SQL Server.
- Integrate data from multiple ERP and CRM source systems.
- Develop scalable and maintainable ETL workflows using SQL.
- Implement a three-layer Medallion Architecture.
- Perform data cleansing, standardization, and transformation.
- Establish data consistency and quality validation procedures.
- Develop a dimensional data model using a Star Schema.
- Create fact and dimension tables to support analytical workloads.
- Enable business reporting through optimized SQL queries.
- Maintain technical documentation covering architecture, data flows, and data models.

## 3. Technology Stack

| Technology | Application |
|---|---|
| Microsoft SQL Server | Data warehouse implementation and database management |
| SQL / T-SQL | Data extraction, transformation, loading, and analytical queries |
| SQL Server Management Studio | Database development and administration |
| Git | Source code version control |
| GitHub | Repository management and project documentation |
| Draw.io | Data architecture and modeling diagrams |
| CSV | Source data format |
| Notion | Project planning and task management |

## 4. Data Architecture

The solution implements the Medallion Architecture, organizing data processing into three logical layers.

### 4.1 Bronze Layer – Raw Data Ingestion

The Bronze Layer serves as the initial landing zone for source data.

Key activities:
- Ingest raw CSV datasets from ERP and CRM systems.
- Create structured staging tables in SQL Server.
- Preserve source data with minimal transformation.
- Implement SQL-based data loading procedures.
- Maintain traceability to the original source datasets.

### 4.2 Silver Layer – Data Cleansing and Integration

The Silver Layer transforms raw data into consistent and reliable datasets.

Key activities:
- Identify and handle duplicate records.
- Address missing and inconsistent values.
- Standardize data formats and data types.
- Apply data validation and cleansing rules.
- Integrate related ERP and CRM datasets.
- Resolve inconsistencies across source systems.
- Implement reusable transformation procedures.

### 4.3 Gold Layer – Analytical Data Modeling

The Gold Layer provides business-ready datasets optimized for analytical queries and reporting.

Key activities:
- Design dimensional data models.
- Develop customer and product dimension tables.
- Create sales fact tables.
- Implement Star Schema modeling.
- Define relationships between facts and dimensions.
- Prepare datasets for business intelligence and reporting.

## 5. ETL Pipeline Implementation

The project implements an Extract, Transform, and Load (ETL) workflow to process data across the warehouse layers.

| Stage | Description |
|---|---|
| Extract | Retrieve source datasets from CRM and ERP CSV files. |
| Transform | Clean, standardize, validate, and integrate source data. |
| Load | Populate the Bronze, Silver, and Gold warehouse layers. |

SQL scripts and stored procedures are used to organize and execute the data loading and transformation processes.

## 6. Repository Structure

```text
sql-data-warehouse-project/
│
├── 00_setup/
│   └── Installation and database setup documentation
│
├── 01_datasets/
│   ├── source_crm/
│   │   ├── cust_info.csv
│   │   ├── prd_info.csv
│   │   └── sales_details.csv
│   │
│   └── source_erp/
│       ├── CUST_AZ12.csv
│       ├── LOC_A101.csv
│       └── PX_CAT_G1V2.csv
│
├── 02_docs/
│   ├── requirements.md
│   ├── data_architecture.png
│   ├── data_model.png
│   ├── data_flow.png
│   ├── data_catalog.md
│   └── naming_conventions.md
│
├── 03_scripts/
│   ├── init_database.sql
│   │
│   ├── bronze/
│   │   ├── ddl_bronze.sql
│   │   └── proc_load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl_silver.sql
│   │   └── proc_load_silver.sql
│   │
│   └── gold/
│       └── ddl_gold.sql
│
├── 04_tests/
│   ├── quality_checks_silver.sql
│   └── quality_checks_gold.sql
│
└── README.md
```

## 7. Dimensional Data Modeling

The Gold Layer follows a Star Schema approach to simplify analytical queries and improve reporting accessibility.

### Dimension Tables

**dim_customers**
- Contains customer-related attributes.
- Supports customer segmentation and behavioral analysis.
- Provides descriptive information for sales reporting.

**dim_products**
- Contains product attributes and category information.
- Supports product-level and category-level performance analysis.

### Fact Table

**fact_sales**
- Stores sales transaction records.
- Contains measurable business metrics.
- Supports revenue, sales volume, and performance analysis.

The dimensional model establishes relationships between business entities and transactional data, enabling efficient analytical querying.

## 8. Business Intelligence and Analytics

The data warehouse provides a structured foundation for analyzing business performance across three key analytical domains.

### Customer Analytics
- Customer purchasing patterns.
- Customer segmentation and distribution.
- Revenue contribution by customer.
- Customer-level sales performance.

### Product Analytics
- Product sales performance.
- Product category analysis.
- Top-performing products.
- Revenue contribution by product.

### Sales Analytics
- Overall sales performance.
- Revenue trends over time.
- Sales distribution across products and customers.
- Transaction-level analysis.
- Key business performance indicators.

These analytical capabilities support data-driven business evaluation and strategic decision-making.

## 9. Data Quality and Validation

Data quality validation is incorporated into the warehouse development process to improve the reliability and consistency of analytical datasets.

The validation process includes:

- Duplicate record identification.
- NULL value detection.
- Primary key and uniqueness validation.
- Referential integrity verification.
- Data type and format validation.
- Data consistency checks.
- Business rule validation.
- Fact and dimension table validation.

Dedicated SQL scripts are maintained in the `04_tests/` directory for Silver and Gold layer validation.

## 10. Installation and Execution

### Prerequisites

- Microsoft SQL Server.
- SQL Server Management Studio (SSMS).
- Git.
- Windows operating system.
- Basic understanding of SQL and relational databases.

### Setup Instructions

**Step 1 – Clone the repository**

```bash
git clone https://github.com/DataWithBaraa/sql-data-warehouse-project.git
```

**Step 2 – Configure the source datasets**

Download or use the provided CRM and ERP CSV datasets. Configure the dataset directory paths according to your local environment.

**Step 3 – Connect to SQL Server**

Open SQL Server Management Studio and establish a connection to your database instance.

**Step 4 – Initialize the database**

Execute the database initialization script:

```sql
03_scripts/init_database.sql
```

**Step 5 – Implement the Bronze Layer**

Execute the Bronze DDL and data loading scripts to create staging tables and ingest the source datasets.

**Step 6 – Implement the Silver Layer**

Execute the Silver DDL and transformation procedures to clean, standardize, and integrate the source data.

**Step 7 – Implement the Gold Layer**

Execute the Gold DDL scripts to create the analytical fact and dimension tables.

**Step 8 – Perform Data Quality Validation**

Execute the SQL validation scripts available in the `04_tests/` directory.

Refer to the `00_setup/` directory for detailed installation and configuration instructions.

## 11. Key Data Engineering Concepts

This project demonstrates practical implementation of the following concepts:

- Data Warehouse Architecture
- Medallion Architecture
- ETL Pipeline Development
- Relational Database Management
- SQL Server and Advanced T-SQL
- Data Ingestion and Integration
- Stored Procedures
- Data Cleaning and Transformation
- Data Quality Assurance
- Dimensional Data Modeling
- Star Schema Design
- Fact and Dimension Tables
- SQL Query Development
- Data Documentation
- Git-Based Version Control
- Business Intelligence and Analytics

## 12. Learning Resources and References

This project is based on the educational materials provided by Data With Baraa.

- [Original GitHub Repository](https://github.com/DataWithBaraa/sql-data-warehouse-project)
- [YouTube Project Tutorial](https://youtu.be/9GVqKuTVANE)
- [Data Warehouse Engineering Bootcamp](https://www.udemy.com/course/building-a-modern-data-warehouse-data-engineering-bootcamp/)
- [Data With Baraa Official Website](https://www.datawithbaraa.com)

## 13. Author

**Saurabh Shinde**

B.E. Artificial Intelligence and Data Science Engineering | 2026 Graduate

Aspiring Data Engineer interested in building reliable data pipelines, developing data warehouse solutions, and transforming raw data into meaningful business insights.

**Technical Interests:**
- Data Engineering
- SQL Development
- Data Warehousing
- ETL Pipeline Development
- Database Management
- Business Intelligence

**Professional Profiles:**
- GitHub: [https://github.com/saurabhshinde0809-design/)
- LinkedIn: [https://www.linkedin.com/in/saurabh-shinde-a187523b1?utm_source=share_via&utm_content=profile&utm_medium=member_android)

## 14. License and Attribution

This project is based on the original educational project developed by Data With Baraa.

All original materials, source code, and associated licensing terms remain subject to the original repository's license.

Refer to the original repository for licensing and attribution details.

---

**Project Status:** Educational Data Engineering Project

**Focus:** Data Warehousing | ETL | SQL Server | Data Modeling | Analytics
