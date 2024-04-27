# Azure Data Fundamentals Notes
This README provides a comprehensive overview of Azure Data Fundamentals, covering core cloud concepts, data storage and processing, and a wide range of Azure Data Services essential for building scalable and efficient data solutions in the cloud.

# Core Cloud Concepts

## PaaS (Platform as a Service)

In a PaaS environment like Microsoft Azure, the cloud provider offers a platform that includes both software and hardware infrastructure necessary for application development and deployment. This setup enables clients to focus on creating and managing their applications and services without concerning themselves with the underlying operating system, server hardware, or network infrastructure.

## SaaS (Software as a Service)

SaaS delivers software applications as a service over the internet. It's the most comprehensive form of cloud service, providing complete applications on demand. A third party manages all aspects of the application environment, including the underlying infrastructure, middleware, application software, and application data.

**Examples in Azure:**
- **Microsoft 365 (formerly Office 365):** A cloud-based office suite offering services like email (Exchange), file storage (OneDrive), and productivity applications (Word, Excel, PowerPoint, etc.).
- **Dynamics 365:** A suite of enterprise resource planning (ERP) and customer relationship management (CRM) applications.

## IaaS (Infrastructure as a Service)

IaaS enables businesses and developers to rent virtualized computing resources over the internet, including servers, storage, and networking hardware. This service model provides a high degree of control and flexibility over the computing environment, akin to managing physical hardware, compared to PaaS and SaaS.

- **Core Data Concepts**
    
    # **Explore Data Concepts**
    
    In this module you will learn how to:
    
    - Identify common data formats
    - Describe options for storing data in files
    - Describe options for storing data in databases
    - Describe characteristics of transactional data processing solutions
    - Describe characteristics of analytical data processing solutions
    
    ## **Identify Various Data Formats**
    
    > Data is a collection of facts such as numbers, descriptions, and observations used to record information.
    > 
    
    In the context of relational databases, **entities are the tables** and **attributes are the fields/columns.**
    
    **You can classify data as *structured*, *semi-structured*, or *unstructured*.**
    
    ### Structured Data
    
    - data that adheres to a fixed *schema*, so all of the data has the same fields or properties.
    - commonly, schema for structured data is tabular:
    
    ![field-record-value.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/e52d73cc-3b34-47d5-a63e-9b0c0b29e553/field-record-value.png)
    
    ### Semi-structured Data
    
    > *Semi-structured* data is information that has some structure
    > 
    
    Example: most customers may have an email address, some might have multiple email addresses, and some might have none at all.
    
    **JSON is just one of many ways in which semi-structured data can be represented.**
    
    ```python
    // Customer 1
    {
      "firstName": "Joe",
      "lastName": "Jones",
      "address":
      {
        "streetAddress": "1 Main St.",
        "city": "New York",
        "state": "NY",
        "postalCode": "10099"
      },
      "contact":
      [
        {
          "type": "home",
          "number": "555 123-1234"
        },
        {
          "type": "email",
          "address": "joe@litware.com"
        }
      ]
    }
    
    // Customer 2
    {
      "firstName": "Samir",
      "lastName": "Nadoy",
      "address":
      {
        "streetAddress": "123 Elm Pl.",
        "unit": "500",
        "city": "Seattle",
        "state": "WA",
        "postalCode": "98999"
      },
      "contact":
      [
        {
          "type": "email",
          "address": "samir@northwind.com"
        }
      ]
    }
    ```
    
    ### Unstructuered Data
    
    - Documents, images, audio and video data, and binary files. This kind of data is referred to as *unstructured* data.
    
    ## File Storage
    
    > Files can be stored locally on personal computers or removable media, but in organizations, they're typically stored centrally in shared file storage systems, increasingly hosted in the cloud for cost-effective, secure, and reliable storage of large data volumes.
    > 
    
    ### Delimited Text Files
    
    - Data is often stored in plain text format with specific field delimiters and row terminators.
    - The most common format for delimited data is comma-separated values (CSV), where fields are separated by commas and rows are terminated by a carriage return / new line.
    - Optionally, the first line may include the field names.
    - Other common formats include tab-separated values (TSV) and space-delimited formats.
    - Fixed-width data allocates a fixed number of characters to each field.
    - Delimited text is suitable for structured data accessed by various applications and services in a human-readable format.
    1. **CSV (Comma-Separated Values)**:
    
    ```
    Name, Age, City
    John, 25, New York
    Emma, 30, London
    Michael, 40, Sydney
    ```
    
    1. **TSV (Tab-Separated Values)**:
    
    ```
    Name    Age    City
    John    25    New York
    Emma    30    London
    Michael    40    Sydney
    ```
    
    1. **Space-Delimited**:
    
    ```
    Name Age City
    John 25 New York
    Emma 30 London
    Michael 40 Sydney
    ```
    
    1. **Fixed-Width**:
    
    ```
    Name    Age    City
    John    25     New York
    Emma    30     London
    Michael 40     Sydney
    ```
    
    In CSV, TSV, and space-delimited formats, the fields are separated by commas, tabs, or spaces respectively, while in the fixed-width format, each field has a predefined width.
    
    ### JSON
    
    > 
    > 
    1. **Structured JSON**: In structured JSON, the data follows a specific schema or pattern. This means that the JSON data adheres to a predefined structure where keys are known in advance, and their values are of expected types. For example, in a structured JSON representing a person, you might expect keys like "name", "age", "email", etc. 
        
        ```json
        {
          "name": "John Doe",
          "age": 30,
          "email": "john@example.com"
        }
        ```
        
    2. **Unstructured JSON**: In contrast, unstructured JSON doesn't follow a strict schema. It may contain arbitrary keys and values, and the structure might vary between different data instances. This type of JSON is more flexible and can accommodate diverse data without predefined expectations. Unstructured JSON is often used in scenarios where the data is not easily categorized or where the structure is not known in advance.
        
        ```json
        {
          "title": "Book Title",
          "author": "Author Name",
          "year": 2022,
          "details": {
            "publisher": "Publisher Name",
            "pages": 250
          },
          "reviews": [
            {
              "user": "User1",
              "rating": 4
            },
            {
              "user": "User2",
              "rating": 5
            }
          ]
        }
        ```
        
    - objects are enclosed in braces (**{..}**)
    - collections are enclosed in square brackets (**[..]**).
    - attributes are represented by *name* **:** *value* pairs and separated by commas (**,**).
    
    ### **Extensible Markup Language (XML)**
    
    > XML uses *tags* enclosed in angle-brackets (**<../>**) to define *elements* and *attributes.*
    > 
    
    ```python
    <Customers>
      <Customer name="Joe" lastName="Jones">
        <ContactDetails>
          <Contact type="home" number="555 123-1234"/>
          <Contact type="email" address="joe@litware.com"/>
        </ContactDetails>
      </Customer>
      <Customer name="Samir" lastName="Nadoy">
        <ContactDetails>
          <Contact type="email" address="samir@northwind.com"/>
        </ContactDetails>
      </Customer>
    </Customers>
    ```
    
    ### **Binary Large Object (BLOB)**
    
    In human-readable formats like CSV or JSON, binary data is translated into printable characters using character encoding like ASCII or Unicode. However, some file formats store data directly as raw binary, necessitating interpretation by applications. Examples include images, video, audio, and application-specific documents.
    
    ### Optimized file formats
    
    > Over time, some specialized file formats that enable compression, indexing, and efficient storage and processing have been developed.
    > 
    
    Some common optimized file formats you might see include *Avro*, *ORC*, and *Parquet*:
    
    - ***Avro* is a row-based format.**
        - Created by Apache
        - Each record contains a JSON header describing the data structure
        - Data stored as binary information
        - Application uses header information to parse binary data and extract fields
        - Avro format is efficient for compressing data and reducing storage and network bandwidth usage
    - ***ORC* (Optimized Row Columnar format) organizes data into columns rather than rows.**
        - Developed by HortonWorks
        - Optimizes read and write operations in Apache Hive
        - Hive: data warehouse system supporting fast data summarization and querying over large datasets
        - ORC file structure:
            - Stripes of data
            - Each stripe holds data for a column or set of columns
            - Stripe includes:
                - Index into the rows
                - Data for each row
                - Footer containing statistical information for each column (count, sum, max, min, etc.)
    - ***Parquet* is another columnar data format.**
        - Created by Cloudera and Twitter
        - Parquet file structure:
            - Row groups
                - Data for each column stored together in the same row group
            - Each row group contains one or more data chunks
            - Metadata describes the set of rows in each chunk
        - Applications use metadata to locate the correct chunk for a given set of rows
        - Parquet specializes in storing and processing nested data types efficiently
        - Supports very efficient compression and encoding schemes
    
    ## Databases
    
    > A database is like a central hub where data is stored and managed. Think of it as a fancy filing system specifically designed for handling data records, different from just storing files like you would on your computer's file system.
    > 
    
    ### Relational Databases
    
    ![relational-database.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/fd023dec-2068-4929-ad93-042aca5db652/relational-database.png)
    
    - Relational databases store and query structured data.
    - Data is organized into tables representing entities like customers, products, or sales orders.
    - Each entity instance is assigned a primary key for unique identification.
    - Primary keys are used to reference entity instances in other tables.
    - Referencing allows for normalization, reducing duplicate data.
        - For instance, customer details are stored once and referenced in sales orders.
    - Structured Query Language (SQL) is used to manage and query tables.
        - SQL is based on an ANSI standard, ensuring similarity across databases.
    
    ### Non-relational Databases
    
    - DBMS that don’t apply a relational schema to the data.
    - Also called as NoSQL databases, but some support a variant of SQL.
    
    **There are four common types of Non-relational database commonly in use:**
    
    - Key-value databases
        - key-value pairs
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/c6da74af-303f-4978-82c7-620ad412a307/Untitled.png)
    
    ### Document
    
    - Key-value pair but the value is a JSON
    
    ![document-store.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/f46979d2-bc87-416c-a055-28afef6f7e16/document-store.png)
    
    ### Column family
    
    - Like a regular tabular database but you can divide the columns into groups known as column-families. Each column family holds a set of columns that are logically related together.
    
    ![column-family-store.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/1af3aea5-d0ea-40b4-95b6-aa1ea41997a7/column-family-store.png)
    
    ### Graph
    
    - store entities as nodes with links to define relationships between them.
    
    ![graph.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/581864de-d26b-4d58-8208-4a0f112c12b2/f2332632-9c0f-4f90-b2a7-301992a57bbb/graph.png)
    
    ## Transactional Data Processing
    
    A transactional data processing system records and tracks specific events in a business, like financial transactions or sales. It handles large volumes of data quickly and is crucial for businesses to operate smoothly. This type of system is known as Online Transactional Processing (OLTP).
    
    They follow some rules to make sure everything stays in order:
    
    1. **Atomicity**: Every task is like a single job. It either gets done perfectly or not at all. For example, if you're moving money from one bank account to another, both actions have to happen together. If one fails, the other can't go through.
    2. **Consistency**: The data in the database always makes sense. So, if you move money between accounts, the balances have to add up correctly afterward. If something fails, it all fails.
    3. **Isolation**: Even when lots of things are happening at once, each task stays separate and doesn't mess with the others. For instance, if you're checking your balance while transferring money, you should get the right balance for both accounts, even if the transfer isn't finished yet.
    4. **Durability**: Once something is committed, it stays committed. So, if you finish moving money, the new balances are saved even if the power goes out. When you turn the system back on, everything is still there, just like before.

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
