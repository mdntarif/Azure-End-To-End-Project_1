# Azure Synapse Analytics & Databricks Pipeline Project

This project demonstrates the full pipeline from data transformation to reporting using **Azure Synapse Analytics**, **Azure Data Lake**, **Databricks**, and **Power BI**. The goal is to efficiently process, store, and analyze sales data using various Azure tools and services.

## Project Overview

The project involves transforming and processing data in multiple stages:

1. **Data Ingestion**: Data is loaded from different sources (CSV, Parquet, etc.) into an Azure Data Lake.
2. **Data Transformation**: Using **Azure Databricks**, data is processed, cleaned, and transformed to meet analytical requirements.
3. **Data Storage**: Data is stored in different layers of the Data Lake: **Silver** for processed data and **Gold** for final reporting.
4. **Data Analytics**: **Azure Synapse Analytics** is used to perform SQL-based analytics on the processed data.
5. **Reporting**: Data is connected to **Power BI** for visualization and reporting, enabling business decision-making.

## Key Steps

### Step 1: Data Transformation with Databricks

- **Transform Products Table**: Extracted the first word before the `-` in `ProductSKU` and the first word before the space in `ProductName`.
- **Push Data to Silver Layer**: Transformed data was saved in the **Silver** layer in Parquet format.
- **Analysis**: Visualized the number of orders placed on each order date with a chart in Databricks.
- **Other Transformations**: Multiple transformations like date formatting, text replacement, and multiplication were performed on the `Sales` table.

### Step 2: Data Storage and Security

- **External Data Lake Configuration**: Configured **Azure Synapse Analytics** to access data stored in Azure Data Lake.
- **Permissions Setup**: Assigned **Storage Blob Data Contributor** role to the Synapse workspace for access control.

### Step 3: Data Access and Reporting

- **SQL Views and External Tables**: Created SQL views and external tables to enable seamless access to data stored in the Data Lake.
- **Power BI Integration**: Connected **Power BI** to **Azure Synapse Analytics** using the Serverless SQL endpoint, allowing data analysts to visualize and report on the transformed data.

## Tools & Technologies

- **Azure Synapse Analytics**: Used for big data analytics and SQL-based queries on data.
- **Databricks**: Used for data transformations, visualizations, and analytics.
- **Azure Data Lake Storage Gen2**: Data lake for storing raw and processed data.
- **Power BI**: Used for visualizing and reporting the data.
- **Parquet**: A columnar data storage format used for optimized data storage and query performance.

## Setup Instructions

1. **Set Up Azure Synapse Analytics**:
   - Create an Azure Synapse workspace and configure it with SQL pool and storage accounts.
   - Set up appropriate access control (IAM) for Azure Data Lake.

2. **Install Databricks**:
   - Create an Azure Databricks workspace.
   - Run the transformation scripts provided in this repository on the Databricks platform.

3. **Power BI Integration**:
   - Connect Power BI to Azure Synapse Analytics using the Serverless SQL endpoint.
   - Load the tables and start visualizing the data.

## Conclusion

This project demonstrates how to set up an efficient ETL pipeline using Azure Synapse, Databricks, and Power BI, allowing seamless data processing, transformation, and reporting for business analysis.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Microsoft Azure Documentation
- Databricks Documentation
- Power BI Documentation
