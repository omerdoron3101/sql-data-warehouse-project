# 📘 Data Catalog - Gold Layer

## Overview
The **Gold Layer** represents the *business-ready* data model within the Data Warehouse.  
It is designed to support analytical, reporting, and KPI use cases.  
This layer contains **dimension tables** (descriptive data) and **fact tables** (transactional data with measurable metrics).

---

## 1. `gold.dim_customers`
**Purpose:** Stores standardized and enriched customer information for analytical use.

| Column Name      | Data Type     | Description                                                                                   |
|------------------|---------------|-----------------------------------------------------------------------------------------------|
| `customer_key`   | INT           | Surrogate key uniquely identifying each customer record in the warehouse.                     |
| `customer_id`    | INT           | Business key from the source system, representing the customer’s original ID.                 |
| `customer_number`| NVARCHAR(50)  | Alphanumeric identifier used in ERP/CRM systems for referencing the customer.                 |
| `first_name`     | NVARCHAR(50)  | The customer's given name.                                                                    |
| `last_name`      | NVARCHAR(50)  | The customer's family name.                                                                   |
| `country`        | NVARCHAR(50)  | The customer’s country of residence (e.g., 'Australia').                                      |
| `marital_status` | NVARCHAR(50)  | Marital status of the customer (e.g., 'Married', 'Single').                                   |
| `gender`         | NVARCHAR(50)  | Gender information (e.g., 'Male', 'Female', or 'n/a').                                        |
| `birthdate`      | DATE          | The customer’s date of birth (YYYY-MM-DD).                                                    |
| `create_date`    | DATE          | The timestamp when the record was created in the source system.                               |

---

## 2. `gold.dim_products`
**Purpose:** Contains product details and classification attributes for analysis.

| Column Name          | Data Type     | Description                                                                                   |
|----------------------|---------------|-----------------------------------------------------------------------------------------------|
| `product_key`        | INT           | Surrogate key uniquely identifying each product in the warehouse.                             |
| `product_id`         | INT           | Business key from the source system.                                                          |
| `product_number`     | NVARCHAR(50)  | Structured alphanumeric code used to represent the product.                                   |
| `product_name`       | NVARCHAR(50)  | Descriptive name of the product, including type, color, or size.                              |
| `category_id`        | NVARCHAR(50)  | Identifier of the product’s category, used for hierarchical grouping.                         |
| `category`           | NVARCHAR(50)  | High-level category (e.g., 'Bikes', 'Components').                                            |
| `subcategory`        | NVARCHAR(50)  | More specific classification within the category.                                             |
| `maintenance_required`| NVARCHAR(50) | Indicates whether the product requires maintenance ('Yes' or 'No').                           |
| `cost`               | INT           | Base cost or price of the product in monetary units.                                          |
| `product_line`       | NVARCHAR(50)  | The product line or series (e.g., 'Road', 'Mountain').                                        |
| `start_date`         | DATE          | The date when the product became available for sale.                                          |

---

## 3. `gold.fact_sales`
**Purpose:** Holds transactional sales data aggregated at the line-item level for reporting and analysis.

| Column Name     | Data Type     | Description                                                                                   |
|-----------------|---------------|-----------------------------------------------------------------------------------------------|
| `order_number`  | NVARCHAR(50)  | Unique alphanumeric identifier for each sales order (e.g., 'SO54496').                        |
| `product_key`   | INT           | Foreign key linking the order to `gold.dim_products`.                                         |
| `customer_key`  | INT           | Foreign key linking the order to `gold.dim_customers`.                                        |
| `order_date`    | DATE          | The date when the order was placed.                                                           |
| `shipping_date` | DATE          | The date when the order was shipped to the customer.                                          |
| `due_date`      | DATE          | The date by which payment for the order was due.                                              |
| `sales_amount`  | INT           | Total monetary value of the sale for the line item.                                           |
| `quantity`      | INT           | Quantity of items sold in this line item.                                                     |
| `price`         | INT           | Unit price of the product at the time of sale.                                                |

---

## 🔗 Relationships
The following relationships define the star-schema structure of the Gold Layer:

- `fact_sales.customer_key` → `dim_customers.customer_key`  
- `fact_sales.product_key` → `dim_products.product_key`

These relationships enable efficient analytical queries and business intelligence reporting.
