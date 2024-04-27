# azure-data-fundamentals-notes
This directory provides a high-level overview of the various Azure Data Services available to support scalable and efficient data solutions in the cloud. Each service is designed to meet specific data needs, from real-time processing to massive data warehousing, ensuring that organizations can leverage their data effectively and efficiently.

# Azure Data Services

## Introduction
Microsoft Azure is a comprehensive cloud platform that enables the running of both applications and IT infrastructure for some of the world's most prominent organizations. It offers a variety of services designed to support both transactional and analytical data workloads essential for modern cloud solutions.

### Azure SQL
![Azure SQL](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/a74dccee-7812-455c-bd45-cee5f28227a6/Untitled.png)
Azure SQL is the umbrella term for several relational database solutions based on Microsoft SQL Server. These solutions are pivotal for data engineers to build data pipelines that perform *extract*, *transform*, and *load* (ETL) operations. The specific services under Azure SQL include:
- **Azure SQL Database**: Fully managed database service, hosted in Azure.
- **Azure SQL Managed Instance**: Offers SQL Server instance capabilities with automated maintenance.
- **Azure SQL VM**: Provides full control over SQL Server installations on virtual machines.

## Azure Database for Open-Source Relational Databases
![Open-Source DBs](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/321f2bd0-8329-4086-b1aa-c78f462672ce/Untitled.png)
This category includes managed services for popular open-source relational databases:
- **Azure Database for MySQL**
- **Azure Database for MariaDB**
- **Azure Database for PostgreSQL**
These services support transactional applications and serve as data sources for analytical solutions.

### Azure Cosmos DB
![Azure Cosmos DB](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/2578ed98-f252-4873-99dd-8f3fd8eff4b7/Untitled.png)
Azure Cosmos DB is a globally distributed NoSQL database service known for its high scalability and multi-model support, which includes document, key-value, graph, and column-family data models.

### Azure Storage
![Azure Storage](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/azure-storage.png)
Azure Storage is vital for hosting data lakes and provides various storage types:
- **Blob containers**: For large-scale unstructured data.
- **File shares**: Traditional file storage.
- **Tables**: Quick data access via key-value pairs.

### Azure Data Factory
![Azure Data Factory](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/00bdec0e-6c2d-430d-9da4-ad4d03b89477/Untitled.png)
Utilized to design, schedule, and orchestrate complex data flows across diverse Azure services.

### Azure Synapse Analytics
![Azure Synapse Analytics](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/azure-synapse.png)
This integrates big data and data warehousing into a single service platform, providing powerful tools for large-scale data processing and analytics.

### Azure Databricks
![Azure Databricks](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/azure-databricks.png)
Offers an optimized Apache Spark environment to accelerate big data analytics applications.

### Azure HDInsight
![Azure HDInsight](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/hdinsight.png)
Provides managed Apache Hadoop clusters for processing massive amounts of data with a suite of major Apache big data frameworks.

### Azure Stream Analytics
![Azure Stream Analytics](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/stream-analytics.png)
Ideal for real-time data stream processing from IoT devices, websites, social media feeds, applications, and more.

### Azure Data Explorer
![Azure Data Explorer](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/azure-data-explorer.png)
Focused on rapid data exploration, Azure Data Explorer facilitates real-time analysis on large volumes of data, particularly from log and telemetry sources.

### Microsoft Purview
![Microsoft Purview](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/azure-purview.png)
A governance service that helps organizations manage and govern their on-premises, multi-cloud, and SaaS data.

### Microsoft Fabric
![Microsoft Fabric](https://learn.microsoft.com/en-us/training/wwl-data-ai/explore-roles-responsibilities-world-of-data/media/fabric-icon.png)
A comprehensive analytics platform that integrates data management, data governance, and advanced analytics into a unified SaaS solution.

---

This README provides a high-level overview of the various Azure Data Services available to support scalable and efficient data solutions in the cloud. Each service is designed to meet specific data needs, from real-time processing to massive data warehousing, ensuring that organizations can leverage their data effectively and efficiently.
