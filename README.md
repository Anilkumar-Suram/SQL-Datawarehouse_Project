# SQL Data Warehouse Project

A modern **Data Warehouse project built using SQL Server**, demonstrating end-to-end data engineering practices including **ETL, data cleansing, data integration, dimensional data modeling, data quality, and SQL-based analytics**.

The project follows the **Medallion Architecture** approach with Bronze, Silver, and Gold layers to transform raw source data into business-ready analytical datasets.

---

## 🏗️ Data Architecture

The data warehouse follows a **Medallion Architecture** consisting of three layers:

### 🥉 Bronze Layer — Raw Data

The Bronze layer stores data in its raw form as received from the source systems.

* Data is ingested from CSV files.
* Minimal transformation is performed.
* Data is preserved as close to the original source format as possible.
* Acts as the foundation for downstream processing.

### 🥈 Silver Layer — Cleaned & Standardized Data

The Silver layer is responsible for transforming raw data into clean, consistent, and standardized datasets.

Key activities include:

* Data cleansing
* Data validation
* Handling missing and invalid values
* Standardizing formats
* Removing duplicates
* Data type conversions
* Data integration and normalization
* Resolving data quality issues

### 🥇 Gold Layer — Business-Ready Data

The Gold layer contains business-ready datasets optimized for analytics and reporting.

It includes:

* Fact tables
* Dimension tables
* Star schema
* Business-level transformations
* Aggregated and analytical datasets

The Gold layer serves as the primary source for reporting and analytical queries.

---

## 📌 Project Overview

This project demonstrates the development of a complete modern data warehouse using SQL Server.

The project covers the following key areas:

### Data Architecture

Designing and implementing a modern data warehouse using the **Bronze → Silver → Gold** architecture.

### ETL Pipelines

Building SQL-based ETL processes to:

* Extract data from source files
* Load raw data into the Bronze layer
* Transform and cleanse data in the Silver layer
* Create business-ready datasets in the Gold layer

### Data Modeling

Designing an analytical data model using:

* Fact tables
* Dimension tables
* Star schema
* Surrogate keys
* Business keys
* Relationships between dimensions and facts

### Data Quality

Identifying and resolving common data quality issues such as:

* Missing values
* Duplicate records
* Invalid values
* Inconsistent formats
* Incorrect data types
* Referential integrity issues

### Analytics & Reporting

Developing SQL-based analytical queries to generate insights into:

* Customer behavior
* Product performance
* Sales trends
* Revenue performance
* Business KPIs

---

## 🎯 Project Objectives

The primary objective of this project is to build a **scalable and maintainable data warehouse using SQL Server** that consolidates data from multiple source systems and makes it easily accessible for analytical workloads.

The project aims to demonstrate practical experience in:

* SQL Development
* Data Engineering
* Data Warehousing
* ETL Development
* Data Modeling
* Data Quality
* Dimensional Modeling
* Data Analytics
* SQL-based Reporting

---

# 📋 Project Requirements

## 1. Data Engineering — Building the Data Warehouse

### Objective

Develop a modern data warehouse using SQL Server to consolidate data from multiple source systems and provide a reliable foundation for analytical reporting and business intelligence.

### Specifications

#### Data Sources

The project uses data from two source systems:

* **ERP System**
* **CRM System**

The source data is provided as CSV files.

#### Data Integration

Integrate data from both source systems into a single, consistent data warehouse.

The integration process should address:

* Different naming conventions
* Different data formats
* Duplicate information
* Conflicting values
* Different business keys
* Data quality issues

#### Data Quality

Identify and resolve data quality issues before the data reaches the analytical layer.

This includes:

* Handling missing values
* Removing duplicates
* Standardizing formats
* Validating business rules
* Resolving inconsistent values
* Ensuring data integrity

#### Data Modeling

Design a business-friendly analytical data model using a **Star Schema** consisting of:

* Dimension tables
* Fact tables
* Appropriate relationships
* Surrogate keys where required

#### Scope

The project focuses on the **latest available dataset**.

Historical data tracking and full historization are outside the current project scope.

#### Documentation

Provide clear documentation covering:

* Data architecture
* Data flow
* ETL processes
* Data catalog
* Data model
* Naming conventions
* Business rules

The documentation should support both technical teams and business/analytics stakeholders.

---

# 📊 2. BI & Analytics — Data Analysis

### Objective

Develop SQL-based analytical queries and reports that transform warehouse data into meaningful business insights.

The analysis focuses on:

### 👥 Customer Behavior

Analyze customer-related metrics and purchasing patterns, including:

* Customer demographics
* Customer purchase behavior
* Customer segmentation
* Customer lifetime activity
* Customer contribution to revenue

### 📦 Product Performance

Analyze product-related metrics, including:

* Product sales
* Product revenue
* Product popularity
* Product category performance
* Best and worst performing products

### 📈 Sales Trends

Analyze sales performance across different dimensions, including:

* Revenue trends
* Sales volume
* Monthly and yearly performance
* Product trends
* Customer trends
* Growth patterns

These insights can help stakeholders monitor key business metrics and make data-driven decisions.

For detailed requirements, refer to:

`docs/requirements.md`

---

# 🛠️ Tools & Technologies

All tools used in this project are either free or have free editions available.

| Tool                                    | Purpose                                                  |
| --------------------------------------- | -------------------------------------------------------- |
| **SQL Server Express**                  | Database engine for hosting the Data Warehouse           |
| **SQL Server Management Studio (SSMS)** | Database development and management                      |
| **SQL**                                 | Data extraction, transformation, analysis, and reporting |
| **Draw.io**                             | Architecture, data flow, ETL, and data modeling diagrams |
| **Git & GitHub**                        | Version control and project management                   |
| **Notion**                              | Project planning, documentation, and task management     |
| **CSV**                                 | Source data format                                       |

---

# 📂 Repository Structure

```text
sql-datawarehouse-project/
│
├── datasets/
│   ├── source_erp/
│   └── source_crm/
│
├── docs/
│   ├── requirements.md
│   ├── etl.drawio
│   ├── data_architecture.drawio
│   ├── data_flow.drawio
│   ├── data_models.drawio
│   ├── data_catalog.md
│   └── naming-conventions.md
│
├── scripts/
│   ├── bronze/
│   │   └── ...
│   │
│   ├── silver/
│   │   └── ...
│   │
│   └── gold/
│       └── ...
│
├── tests/
│   └── ...
│
├── README.md
├── LICENSE
├── .gitignore
└── requirements.txt
```

---

# 🔄 ETL Pipeline

The overall data flow of the project follows:

```text
        ┌──────────────────┐
        │   ERP CSV Files  │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │                  │
        │  Bronze Layer    │
        │   Raw Data       │
        │                  │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │                  │
        │  Silver Layer    │
        │ Clean & Transform│
        │                  │
        └────────┬─────────┘
                 │
                 │
        ┌────────▼─────────┐
        │                  │
        │   Gold Layer     │
        │  Star Schema     │
        │                  │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │    Analytics     │
        │   & Reporting    │
        └──────────────────┘
                 
        ┌──────────────────┐
        │   CRM CSV Files  │
        └────────┬─────────┘
                 │
                 └──────────► Bronze Layer
```

The detailed architecture, ETL flow, and data models are available in the `docs/` directory.

---

# 🧪 Data Quality & Testing

Data quality checks are performed throughout the ETL pipeline to ensure the reliability of the warehouse.

Examples include:

* Row count validation
* Null value checks
* Duplicate detection
* Data type validation
* Referential integrity checks
* Business rule validation
* Primary key validation
* Foreign key validation
* Source-to-target reconciliation

Testing scripts are maintained under:

```text
tests/
```

---

# 📚 Documentation

Detailed project documentation is maintained under the `docs/` directory.

| Document                   | Description                                  |
| -------------------------- | -------------------------------------------- |
| `requirements.md`          | Business and technical requirements          |
| `data_architecture.drawio` | Overall data warehouse architecture          |
| `data_flow.drawio`         | End-to-end data flow                         |
| `data_models.drawio`       | Dimensional model and Star Schema            |
| `etl.drawio`               | ETL processes and implementation approach    |
| `data_catalog.md`          | Dataset and column-level documentation       |
| `naming-conventions.md`    | Naming standards used throughout the project |

---

# 🚀 Project Workflow

The project is developed through the following stages:

```text
1. Requirements Gathering
          ↓
2. Source Data Exploration
          ↓
3. Data Architecture Design
          ↓
4. Bronze Layer Development
          ↓
5. Silver Layer Development
          ↓
6. Gold Layer Development
          ↓
7. Data Modeling
          ↓
8. Data Quality & Testing
          ↓
9. Analytical SQL Development
          ↓
10. Documentation
```

---

# 💡 Key Skills Demonstrated

This project demonstrates practical knowledge of:

* SQL Server
* Advanced SQL
* ETL Development
* Data Warehousing
* Medallion Architecture
* Dimensional Modeling
* Star Schema
* Fact & Dimension Tables
* Data Cleansing
* Data Transformation
* Data Quality
* Data Integration
* Analytical SQL
* Git & GitHub
* Data Documentation

---

# 📈 Future Enhancements

Potential future improvements include:

* Implementing incremental data loading
* Adding historical data tracking
* Implementing Slowly Changing Dimensions (SCD)
* Automating ETL execution
* Adding a Power BI reporting layer
* Implementing additional data quality checks
* Adding automated testing
* Containerizing the database environment
* Implementing CI/CD for database deployments

---

# 📜 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this project, provided that appropriate attribution is given.
