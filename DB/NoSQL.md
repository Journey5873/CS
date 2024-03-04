# NoSQL

# What is NoSQL?

NoSQL databases (aka "not only SQL") are store data differently than relational tables. 

## Difference between RDBMS and NoSQL databases

1. **Flexibility of the schema**
    - RDBMS
        
        In relational databases, data is stored in tables consisting of columns and rows. These databases require defining the schema upfront. It means the database structure can be established after data types are known.
        
    - NoSQL
        
        In NoSQL databases, data can be stored without defining the schema upfront. This allows developers to develop services and define the data model simultaneously. 
        
2.  **Scaling technique**
    - RDBMS
        
        To handle increased loads, it needs to scale vertically. This means it requires increasing the power of the existing server to manage the higher load (e.g., upgrading CPU, RAM).
        
    - NoSQL
        
        Instead of scaling up by adding more servers, NoSQL databases can scale out horizontally. 
        
3. **Support for transactions**
    - RDBMS
        
        RDBMS supports ACID properties (Atomicity, Consistency, Isolation, Durability) for transactions. It ensures reliability and security.
        
    - NoSQL
        
         NoSQL does not guarantee ACID properties. It may be suitable when real-time consistency is not a top priority.
        

## **Benefits of a NoSQL database**

1. **Flexibility**
    
    In NoSQL databases, data can be stored without defining the schema upfront. This enable rapid application development. Developers can focus on creating systems to better serve their customers without worrying about schemas.
    
2. **Scalability**
    
    NoSQL databases can scale out horizontally. They rely on a process called “sharding” to scale out horizontally, which means that more machines can be added to handle data across multiple servers. This allows them to handle extremely large amounts of data.
    
3. **High performance**
    
    NoSQL databases often deliver high performance, especially when queries or operations are frequently performed. 
    

## **Types of NoSQL databases**

There are four main types of NoSQL databases:

- **Key value**
    
    ![Untitled (1)](https://github.com/Journey5873/CS/assets/99030586/5915aafb-e1f6-41a5-a852-d19d3c336cf6)
    
    Key-Value databases are most flexible NoSQL database. Data is stored as a collection of key-value pairs.
    
    Each key has unique value. Any type of data is allowed to store in value filed. So in application layer, it needs to verify type of data.
    
    Key-Value databases are commonly used for scenarios where fast and simple data retrieval is a priority.
    
    **Examples:** Riak, Redis, Voldmort, Oracle NoSQL Database
    
- **Document**
    
    ![Untitled (2)](https://github.com/Journey5873/CS/assets/99030586/d8cd6933-2c44-4fc0-b7c8-8d71b50482ca)
    
    Document databases use a key-value type structure, similar to Key-Value databases. However, in document databases, data is stored in document formats such as JSON or XML. 
    
    And the values in the document can be a variety of types and structures, including strings, numbers, dates, arrays
    
    There is no need to specify fields that a document will contains.
    
    **Examples:** MongoDB, Couch DB, Azure Cosmos DB
    
- **Graph**
    
    ![Untitled (3)](https://github.com/Journey5873/CS/assets/99030586/34de34a6-f14a-4cfb-a4c0-8c00dc394bae)
    
    Graph databases represent connections between nodes that store data. Each node has key-value type of data.
    
    Graph databases are applied in social networks, reservation systems.
    
    **Examples:** Neo4j, BlazeGraph, OrientDB, Titan, AllegroGraph
    
- **Wide column**
    
    Wide column databases store data in column oriented models and are efficient to hold a very large number of dynamic columns. Related columns can be grouped together to form column families. A column family contains multiple rows, each containing a unique row key to identify the row columns within the family.
    
    A wide column database typical structure contains following terms:
    
    - **Column family**: A column family consists of multiple rows.
    - **Row**: Each row contains a unique row identifier to identify the columns data. Every row can have a different number of columns from other rows.
    - **Column:** Each column is contained in its row. A column consists of a name value pair along with a timestamp of its creation date time.
    
    ![image](https://github.com/Journey5873/CS/assets/99030586/97a68368-4a51-458f-ac50-1a9ed835749d)
    
    In a wide column database, a row is constructed with a unique row key, columns including key value pairs and timestamp. A generalized row structure is shown below:
    
    ![Untitled](https://github.com/Journey5873/CS/assets/99030586/fca8655c-4f4f-470e-8ac5-3f47e61203ef)
    
    **Examples:**  Apache Cassandra, HBase, Vertica
    

📂 Reference

[Database Security Best Practices](https://www.oracle.com/database/nosql/what-is-nosql/)

[What Is NoSQL? NoSQL Databases Explained](https://www.mongodb.com/nosql-explained)

[Document Database - NoSQL](https://www.mongodb.com/document-databases)

[[NoSQL 데이터베이스별 특징]](https://jaemunbro.medium.com/nosql-데이터베이스-특성-비교-c9abe1b2838c)

[NoSQL Database types](https://technicalsand.com/nosql-database-types/)
