🧠 Data Warehouse and Analytics Project

Welcome to my Data Warehouse and Analytics Project! 🚀
This project demonstrates a complete data warehousing and analytics solution - from building a modern SQL-based data warehouse to generating business insights through analytical queries and reports.

🏗️ Data Architecture

The project follows the Medallion Architecture approach with Bronze, Silver, and Gold layers:

Bronze Layer: Stores raw data exactly as received from the source systems. Data is ingested from CSV files into a SQL Server database.

Silver Layer: Handles data cleansing, standardization, and normalization to prepare the data for analysis.

Gold Layer: Contains business-ready, analytics-optimized data modeled into a star schema for reporting.

📖 Project Overview

This project includes:

Data Architecture: Designing a modern Data Warehouse using the Medallion Architecture (Bronze, Silver, Gold).

ETL Pipelines: Extracting, transforming, and loading data from source systems into the warehouse using SQL.

Data Modeling: Developing fact and dimension tables optimized for analytical performance.

Analytics & Reporting: Writing SQL-based reports and dashboards to uncover insights such as customer behavior, product performance, and sales trends.

🛠️ Tools & Technologies

SQL Server Express - Database server for hosting and managing the warehouse

SQL Server Management Studio (SSMS) - SQL interface for development and testing

DrawIO - Used for designing data architecture diagrams and data models

Notion - Used for planning and documenting project phases

Git & GitHub - Version control and portfolio management

🚀 Project Goals

The main goal of this project is to build a functional data warehouse that consolidates sales and customer data into a single analytical model, supporting data-driven decision-making.

Key Objectives:

Import and integrate data from multiple source systems (ERP & CRM).

Cleanse and validate raw data to ensure high data quality.

Build a unified star schema model for analytics.

Develop SQL-based queries to analyze customer activity, product sales, and business trends.

📂 Repository Structure
data-warehouse-project/
│
├── datasets/                           # Raw datasets (ERP and CRM data)
│
├── docs/                               # Project documentation and architecture diagrams
│   ├── etl.drawio                      # ETL flow diagram
│   ├── data_architecture.drawio        # Overall data architecture
│   ├── data_catalog.md                 # Dataset catalog and metadata
│   ├── data_flow.drawio                # Data flow diagram
│   ├── data_models.drawio              # Star schema model
│   ├── naming-conventions.md           # Naming standards
│
├── scripts/                            # SQL scripts for ETL and transformations
│   ├── bronze/                         # Raw data extraction and loading
│   ├── silver/                         # Data cleaning and standardization
│   ├── gold/                           # Final data model creation
│
├── tests/                              # Data validation and quality checks
│
├── README.md                           # Project overview (this file)
├── LICENSE                             # License information
├── .gitignore                          # Ignored files and folders
└── requirements.txt                    # Dependencies and environment requirements

🧩 Project Insights

This project highlights best practices in:

Data Engineering: ETL processes and data modeling

Data Quality Management: Ensuring accuracy and consistency

Data Analytics: Building queries that drive business insights

The result is a scalable and transparent data warehouse that supports analytical decision-making and performance tracking.

🛡️ License

This project is licensed under the MIT License
 - you are free to use, modify, and share it with proper attribution.

🌟 About Me

👋 Hi! I'm Omer Doron
I’m a student of Information Systems specializing in Digital Innovation.
I’m passionate about data, analytics, and transforming raw information into meaningful insights.

I created this project as part of my learning journey in data warehousing and analytics, and as a showcase of my technical and analytical skills.

Let’s connect on LinkedIn
 or check out more of my work here on GitHub!
