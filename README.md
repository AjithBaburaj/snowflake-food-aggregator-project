# snowflake-food-aggregator-project
# Snowflake Food Aggregator Data Pipeline

## Overview

Discover how food aggregators and quick-commerce platforms like Swiggy leverage Snowflake to power their data pipelines! This hands-on tutorial starts with a high-level food order process flow, explores the OLTP source ER diagram for data analysis, and explains the 3-layer data warehouse architecture.

Watch as we transform data flow requirements into implementation, create fact and dimension tables, and build an interactive Streamlit dashboard. Perfect for beginners or those curious about executing end-to-end data projects in Snowflake, this real-life data project walkthrough will demystify the process step by step using the Snowflake cloud data platform.

## Architecture

1. **Data Ingestion**: Data is loaded into Snowflake's stage location.
2. **Staging Layer**: Data is copied from the stage to a raw table using Snowflake's Snowsight and COPY command.
3. **Clean Layer**: Basic transformations and cleaning are performed before moving data here.
4. **Consumption Layer**: Fact and dimension tables are created in a Star Schema format.
5. **Dashboarding**: A Streamlit app fetches insights like total revenue, average revenue per order, total orders, and monthly revenue trends.

## Entities Considered

- Location
- Restaurant
- Customer
- Customer Address
- Login Audit
- Menu
- Orders
- Order Items
- Delivery Agent
- Delivery

## Key Features

- **Data Loading**: Utilizes Snowsight's file loading for easy ingestion.
- **Delta Data Handling**: Supports incremental data loads.
- **Query Optimization**: Uses `$` notation and COPY commands for efficiency.
- **Transformation Pipeline**: Implements the Merge statement to transition data across layers.
- **OLTP to OLAP Conversion**: Converts a normalized 3NF schema to a Star Schema for analytics.
- **Streamlit Dashboard**: Provides business insights with KPIs and trends.

## How to Run the Project

### Prerequisites

- Snowflake account
- Python installed (for Streamlit dashboard)
- Required Python libraries installed via:
  ```bash
  pip install -r requirements.txt
  ```

### Steps

1. **Upload Data**: Place sample data in the `data/` folder.
2. **Execute SQL Scripts**:
   - Load data into Snowflake using `scripts/data_ingestion.sql`.
   - Apply transformations using `scripts/data_transformation.sql`.
   - Create fact/dimension tables using `scripts/schema_creation.sql`.
3. **Run Dashboard**:
   ```bash
   streamlit run dashboard/app.py
   ```
4. **Explore Insights**: Access the dashboard to analyze revenue trends and order metrics.

## Repository Structure

```
project-folder/
│-- data/                 # Sample data files
│-- scripts/              # SQL scripts for data processing
│-- dashboard/            # Streamlit dashboard files
│-- README.md             # Project documentation
│-- requirements.txt      # Python dependencies
│-- .gitignore            # Ignore unnecessary files
```

## Future Enhancements

- Automate delta load processing.
- Integrate real-time streaming using Snowpipe.
- Deploy dashboard as a web application.

## License

This project is open-source under the MIT License.

