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

### Normalization

* Normalization is a process for structuring a database in a way that minimizes duplication of data.
* First normal form (1NF) is when every row in a table is unique and every column contains a unique value.
* Second normal form (2NF) starts where 1NF leaves off. 2NF applies an additional rule stating that all nonprimary key values must depend on the entire primary key.
* Third normal form (3NF) builds up 2NF by adding a rule stating all columns must depend on only the primary key.
