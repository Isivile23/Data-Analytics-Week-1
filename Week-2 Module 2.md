# Databases and Data Acquisition
## Exploring Databases

There are many different database options to choose from when an organization needs to store data. While many database products exist, they belong in one of two categories:

* Relational
* Nonrelational

Relational databases excel at storing and processing structured data. The need to interact with unstructured data is one of the reasons behind the rise of nonrelational databases.

### The Relational Model

* In 1969, IBM's Edgar F. Codd developed the relational model for database management.
* The relational model builds on the concept of tabular data.
* In the relational model, an entity contains data for a single subject.
* Relational model allows us to describe how entieies connect or relate to each other.
* Entity Relationship Diagram (ERD) is a visual artifact of data modeling process. It shows connection between related entities.
* Cardinality refers to the relationship between two entities, showing how many instances of one entity relate to instances in another entity.

  Types of relationship cardinality:
  * One-to-One
  * One-to- Many
  * Many-to-Many
    
* A unary relationship is when an entity has a connection with itself.
* A binary relationship connects two entities.
* A ternary relationship connects two entities.
* Binary relationships are the most easy to explore, whereas unary and ternary are comparatively complex and rare.

### Relational Databases

* Relational databases are a piece of software that let you make an operational system out of an ERD.
* You start with a relational model and create a physical design.
* Relational entities correspond to database tables, and entity attributes correspond to table column.

  Benefifs of Relational Databases:
  
  * Consistency
  * Security
  * Case of Backup

* Schema is an ERD with additional details needed to create a database.
* An associative table is both a table and a relationship.
* A primary key is one or more attributes that uniquely identify a specific row in a table.
* A foreign key is one or more columns in one table that points to corresponding columns in a related table.

### Nonrelational Databases

* A nonrelational database does not have a predefined structure based on tabular data.
* The result is a highly flexible approach to storing data.
* Data validation happens in code, as opposed to being done in the database.

 Examples of databases include:

 ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/de1c8bd5-ae7c-4a2a-ad1a-bcbccb236169)

 * A key-value database is one of the simplest ways of storing data.
 * Data is stored as a collection of keys and their corresponding values.
 * A key must be globally unique across the entire database.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/14f7f13b-023c-4c89-9289-23092729eb7d)

* A document database is similar to a key-value database, with additional restrictions.
* In a key-value database, the value can contain anything.
* With a document database, the value is restricted to a specific structured format.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/117e1b2f-d2fe-4ed1-a0bd-24e4edea2797)

* Column-family databases use an index to identify data in groups of related columns.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/6e58ad95-e2ea-4cb8-8b31-466dacfe332d)

* Graph databases specializes in exploring relationships between pieces of data.

## Data Use Cases

Databases tend to support two major categories of ddata processing: Online Transactional Process (OLTP) and Online Analytical Processing (OLAP).

### Online Transactional Processing (OLTP)

* OLTP systems handle the transactions we encounter everyday.
* Example transactions include booking a flight reservation, ordering something online, or executing stock trade.
* While the number of transactions a system handles on a given day can be very high, individual transactions procee small amounts of data.
* OLTP systems balance the ability to write and read data efficiently.
* Employs normalized ralational database schemas to minimize data redundancy and optimize querying for specific data elements. 

### Normalization

* Normalization is a process for structuring a database in a way that minimizes duplication of data.
* First normal form (1NF) is when every row in a table is unique and every column contains a unique value.
* Second normal form (2NF) starts where 1NF leaves off. 2NF applies an additional rule stating that all nonprimary key values must depend on the entire primary key.
* Third normal form (3NF) builds up 2NF by adding a rule stating all columns must depend on only the primary key.

### Online Analytical Processing (OLAP)

* OLAP systems concentrates on analyzing large data sets to identify trends, patterns, and insights for informed decision-making. It's used for tasks like sales analysis, or market research.
* Often utilize multidimensional data models (like star schema or snowflake) that pre-aggregate data for faster analytical queries. These models allow for efficient analysis across multiple dimensions (e.g., time, product, region).

### Schema Concepts

* Transactional systems require highly normalized databases, whereas a denormalized design is more appropriate for analytical systems.
* A data warehouse is a database that aggregates data from many transactional systems for analytical purposes.
* Transactional data may come from systems that power the human resources, sales, marketing, and product divisions.
* A data warehouse facilitates analytics across the entire company.
* A data mart is a subset of data warehouse. Data warehouse serve the entire organization, whereas data mart focus on the needs of a particular department within the organization.
* A data lake store a raw data in its native format instead of conforming to a relational database structure.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/e5fadbda-5b1a-462c-84da-e3bb4139df71)

* A simple, star-like structure with a central fact table surrounded by dimension tables. The fact table stores the quantitative data (measures) relevant to analysis, often with foreign keys referencing the dimension tables. Dimension tables contain descriptive attributes (dimensions) that provide context for the fact table data.

 ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/5366043c-1564-4230-b665-098d8bc90ed8)

* A more complex snowflake-like structure with the fact table at the center and multiple levels of dimension tables radiating outwards. Dimension tables are further normalized to break down complex hierarchies into smaller, atomic tables.

### Dimensionality

* Dimensionality refers to the number of attributes a table has.
* The greater the number of attributes, the higher the dimensionality.
* A dimension table provides additional context around data in fact tables.

### Handling Dimensionality

## Data Acquisition Concepts

### Integration

* You can use a variety of methods to transfer data efficiently and effectively.
* One approach is known as extract, transforn, and load (ETL). This method consists of three phases:
 * Extract: In the first phase, you extract data from the source system and place it in a staging area. The goal of the extract is to move data from a relational database into a flat file as quickly as possible.
 * Transform: The second phase transforms the data. The goal is to reformat the data from its transactional structure to the data warehouse's analytical design.
 * Load: The purpose of the load phase is to ensure data gets into the analytical system as quickly as possible.

* Extract, load, and transform (ELT) is a variant of ETL.
* With ELT, data is extracted from a source database and loaded directly into a warehouse. Once the extract and load phases are complete, the transformation phase gets underway.
* One key difference betweem ETL and ELT is the technical component performing the transformation.
* With ETL, the data transformation takes place external to a relational database, using a programming language like Python.
* ELT uses SQL and the power of relational database to reformat data.

### ETL Vendors

* An initial load occurs the first time data is put into a data warehouse. After the initial load, each additional load is a delta load, also known as incremental load.
* A delta load only moves changes between systems.
* The initial load happens right before the data warehouse becomes available for use.
* When moving data between systems, you have to balance the speed and complexity of the overall operation.

