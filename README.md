# **Azure End-to-End Data Pipeline Project**

## **Overview**
This project implements a comprehensive data pipeline using Azure cloud services to process and analyze AdventureWorks sales data. The solution follows the Medallion Architecture pattern, utilizing the **Bronze**, **Silver**, and **Gold** layers. The architecture incorporates various Azure services for data ingestion, transformation, and analytics. A **dynamic pipeline** has been implemented, reducing ETL time by **70%**, making the data processing more efficient. Additionally, we leverage a **Serverless SQL pool** for **cost-effective queries**, optimizing both performance and cost.

![Project_Architecture_Diagram](https://github.com/user-attachments/assets/df11be48-8035-4c8e-8279-77b91c7339ad)

## **Business Problem Statement**
Businesses today are overwhelmed by large volumes of data that require complex ETL processes and analytics to gain actionable insights. The AdventureWorks dataset simulates a retail business environment where data across multiple dimensions (sales, products, customers, etc.) needs to be processed, cleaned, and analyzed to generate business intelligence. This project aims to streamline the ETL process, make the data accessible for decision-makers, and reduce the time spent on query processing, ultimately improving operational efficiency.

## **Architecture Components**
- **Data Source**: HTTP (GitHub)
- **Data Ingestion**: Azure Data Factory
- **Data Storage**: Azure Data Lake Gen 2
  - **Bronze Layer** (Raw Data)
  - **Silver Layer** (Transformed Data)
  - **Gold Layer** (Serving Layer)
- **Processing**: Azure Databricks
- **Analytics**: Azure Synapse Analytics
- **Visualization**: Power BI
- **Security**: Azure Entra ID, Certificates, and Secrets

## **Dataset**
The project works with 10 AdventureWorks tables:
```
|-- AdventureWorks_Calendar.csv
|-- AdventureWorks_Customers.csv
|-- AdventureWorks_Product_Categories.csv
|-- AdventureWorks_Product_Subcategories.csv
|-- AdventureWorks_Products.csv
|-- AdventureWorks_Returns.csv
|-- AdventureWorks_Sales_2015.csv
|-- AdventureWorks_Sales_2016.csv
|-- AdventureWorks_Sales_2017.csv
|-- AdventureWorks_Territories.csv
```

## **Setup Instructions**

### **Prerequisites**
- Azure Free Account (USD 200 credit for 1 month)
- Basic understanding of Azure services
- Access to GitHub for source data

### **Initial Setup**
1. Create an **Azure Resource Group**.
2. Set up **Storage Account** (Data Lake Gen 2).
   - Use **LRS (Locally Redundant Storage)**.
   - Enable **hierarchical namespace**.
   - Select **Hot Tier** for storage.
   - Enable **public network access**.
3. Create containers for **Bronze**, **Silver**, and **Gold layers**.

### **Data Factory Setup**
1. Create **Azure Data Factory** resource.
2. Implement **Dynamic Pipeline**:
   - Create a **JSON configuration file** for file mapping.
   - Set up **Lookup** and **ForEach** activities.
   - Configure **parameterized Copy activity**.

### **Databricks Configuration**
1. Create an **Azure Databricks** workspace.
2. Set up a **single-node cluster**.
3. Configure **authentication**:
   - Register application in **Microsoft Entra ID**.
   - Assign **Storage Blob Data Contributor** role.
   - Set up **OAuth authentication** in Databricks.

### **Data Transformation**
Implement transformations for each dataset:
1. **Calendar**: Add **Month** and **Year** columns.
2. **Customers**: Create **fullName** column.
3. **Products**: Transform **ProductSKU** and **ProductName**.
4. **Sales**: Convert dates, modify **OrderNumber**, and add calculations.

### **Synapse Analytics Setup**
1. Create **Synapse Analytics** workspace.
2. Configure **permissions** and **access**.
3. Create **SQL views** for data access.
4. Set up **external tables** with:
   - Database-scoped credentials.
   - External data sources.
   - External file formats.

### **Power BI Integration**
1. Connect to **Synapse Analytics endpoint**.
2. Import required tables.
3. Create **visualizations** and **dashboards**.

## **Security Features**
- Integration with **Azure Entra ID**.
- Use of **Managed Identities**.
- **Secure credential management**.
- **Role-based access control**.

## **File Formats**
- Input: **CSV**
- Processed: **Parquet** with **Snappy compression**.

## **Performance Features**
- **Dynamic pipeline reducing ETL time by 70%**: The pipeline is optimized for faster data transformation and processing.
- **Efficient data storage** using **Parquet format**: A columnar storage format providing high efficiency for querying large datasets.
- **Optimized transformations** in Databricks: Data processing is streamlined using Apache Spark for faster computations.
- **Serverless SQL pool for cost-effective queries**: The serverless SQL pool in Azure Synapse ensures that we only pay for the queries executed, optimizing costs.

## **Contact**
mdtarif.chat@gmail.com
