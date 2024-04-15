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
