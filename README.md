# Azure Data Pipeline for Customer Data Processing  

## Project Overview  
The goal of this project is to create a scalable, real-time data pipeline to:  

- **Ingest customer data** from an API.  
- **Process and transform data** into department-specific data marts.  
- **Store structured data** for querying and analysis.  
- **Deliver insights** via interactive dashboards.  

---

## Architecture  

### 1. Azure Event Hub  
- Entry point for real-time data ingestion.  
- Handles high-throughput streaming data from the API.  

### 2. Azure Stream Analytics  
- Processes data in real time.  
- Divides data into **department-specific data marts**.  

### 3. Azure Databricks with Delta Lake and Medallion Architecture  
- **Bronze Layer**: Raw data ingestion.  
- **Silver Layer**: Data cleansing and enrichment.  
- **Gold Layer**: Aggregated, business-ready data.  

### 4. Azure Synapse Analytics  
- Centralized **data warehouse** for historical and real-time analysis.  
- Stores curated data from the **Gold Layer**.  

### 5. Power BI  
- Connects to Synapse Analytics for data visualization.  
- Provides interactive dashboards for decision-making.  

---

## Implementation Steps  

### Prerequisites  
1. **Azure Subscription** with the following services:  
   - Event Hub  
   - Stream Analytics  
   - Databricks  
   - Synapse Analytics  
2. **Power BI Desktop** for dashboard creation.  
3. API endpoint for customer data.  

### Setup and Configuration  

#### 1. Azure Event Hub  
- Create an Event Hub namespace and event hub.  
- Configure the API to send data to the Event Hub.  

#### 2. Azure Stream Analytics  
- Define input as the Event Hub.  
- Configure query logic to partition data into department-specific data marts.  
- Set outputs to write processed data to Azure Databricks or Azure Data Lake.  

#### 3. Azure Databricks  
- Use Delta Lake for storing and transforming data using the Medallion Architecture:  
  - Bronze: Ingest raw data.  
  - Silver: Cleanse and standardize data.  
  - Gold: Aggregate and structure data for business analysis.  

#### 4. Azure Synapse Analytics  
- Link Synapse Analytics with Delta Lake or Azure Data Lake.  
- Load Gold Layer data into Synapse SQL Pool for querying and analysis.  

#### 5. Power BI  
- Connect Power BI to Synapse Analytics.  
- Build and publish interactive dashboards for stakeholders.  

---

## Tools and Technologies  
- **Azure Event Hub**: Data ingestion.  
- **Azure Stream Analytics**: Real-time processing.  
- **Azure Databricks**: Data transformation and storage.  
- **Delta Lake**: Medallion Architecture implementation.  
- **Azure Synapse Analytics**: Data warehousing.  
- **Power BI**: Data visualization.  

---

## Key Benefits  
- **Real-Time Processing**: Delivers actionable insights quickly.  
- **Data Segmentation**: Provides department-specific data for focused decision-making.  
- **Scalability**:
