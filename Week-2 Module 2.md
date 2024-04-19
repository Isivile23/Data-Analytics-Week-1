# Chapter 3: Databases and Data Acquisition
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

### Data Collection Methods

#### Application Programming Interfaces (APIs)

* API acts as an intermediary between two software applications, allowing them to communicate and exchange data with each other.
* Its essentially a set of rules and specifications that define how applications can request and receive information from each other.

#### Web Services

* A web service is an API you can call via Hypertext Transfer Protocol (HTTP), the language of the World Wide Web.
  
#### Web Scraping

* Web scraping is the process of automatically collecting information from the websites.
* Its like scooping up data you find on the web instead of manually copying and pasting it.
* Programmatic retrieval of data from a website is known as web scarping.
* You can use software bots to scrap data from the website.
* Many modern proramming languages, including Python and R, make it easy to create a web scraper.
* Instead of using API or a web service, web scraper reads a web page similar to a web browser, such as Chrome, Safari, or Edge.
#### Human-in-the-Loop

* There are times when the data you seek exists only in people's minds. For example, you can extract the most popular and profitable motorcycling destination from your existing internal data. You can get weather information from an API packaged as a web service. You can glean insight into competitive pricing by scraping your competitors' websites. Even with all of these data sources, you may still want insight into how customers feel about the services you provide. 
#### Surveys

* One way to collect data directly from the customers is by conducting a survey.

#### Survey Tools

* Instead of designing a custom application to collect survey data, several survey products let you design complex surveys without worrying about building a database.
* Qualtrics is a powerful tool for developing and administering surveys

#### Observation

* Observation is the act of collecting primary source data, from either people or machine.
* Observational data can be qualitative or quantitative.
* Collecting qualitative observational data leads to unstructured data challenges.
* Quantitative obsevations are much easier to collect and interpret.

#### Sampling

* Regardless of the data acquisition approach, you may end up with more data than is practical to manipulate. Imagine you are doing analytics in an Internet-of-Things environment, in which 800 billion events occur daily. Though it is possible, ingesting and storing 800 billion records is a challenging task. Manipulating 800 billion records takes a lot of computing power.
* Suppose you want to analyse one day's worth of data. In that case, the 800 billion records represent the total population, or the number of events, available. Since manipulating 800 billion records is unwieldy, you might collect a sample, or subset, of the overall population.

## Working With Data

* To turn a database design into an operational database ready to accept data, you use the Data Definition Language (DDL) components of SQL. DDL lets you create, modify, and delete tables and other associated database objects.
* To generate insights, a productive analyst must be comfortable using the Data Manipulation Language (DML) capabilities of SQL to insert, modify, and retrieve information from databases.
* While DDL manages the structure of database, DML manages data in the database.

### Data Manipulation

When manipulating data, one of four possible actions occurs:

       * Create new data
       * Read existing data
       * Update existing data
       * Delete existing data

* The acronym CRUD (Create, Read, Update, Delete) is a handy way to remember these four operaton.

  ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/28b22259-6677-4c29-abbb-44c91a82e9d3)

### SQL Considerations

The keywords in SQL are case-insensitive. However, the case-sensitivity of column names and values depend on the database configuration.

Consider the following query:

Select Animal_Name, Breed_Name from Animal

The previous query returns the same results as this query:

SELECT Animal_Name, Breed_Name FROM Animal

SQL can also span multiple lines. For example, rewriting the previous query as follows will return identical results:

SELECT Animal_Name, Breed_Name

FROM  Animal

How a query appears is a function of organizational conventions. Factors that influence convention include database configuration, query efficiency, and how easy it is for people to read and understand the query.

### Filtering

Examining a large table in its entirety provides insight into the overall population. To answer questions that an organization's leadership has typically requires a subset of the overall data. Filtering is a way to reduce the data down to only the rows that you need.

To filter data, you add a WHERE clause to a query. Note that the column you are filtering on does not have to appear in the SELECT clause. To retrieve the name and breed for only the dogs from Table 3.1, you modify the query as follows:

SELECT Animal_Name, Breed_Name

FROM  Animal

WHERE Animal_Type = 'Dog'

### Filtering and Logical Operators

A query can have multiple filtering conditions. You need to use a logical operator to account for complex filtering needs. For example, suppose you need to retrieve the name and breed for dogs weighing more than 60 pounds. In that case, you can enhance the query using the AND logical operator, as follows:

SELECT Animal_Name, Breed_Name

FROM  Animal

WHERE Animal_Type = 'Dog'

AND  Weight> 60

The AND operator evaluates the Animal_Type and Weight filters together, only returning records that match both criteria. OR is another frequently used logical operator. For example, suppose you want to see the name and breed for all dogs and any animals that weigh more than 10 pounds regardless of the animal type. The following query delivers the answer to that question:

SELECT Animal_Name, Breed_Name

FROM  Animal

WHERE Animal_Type = 'Dog'

OR   Weight> 10

Complex queries frequently use multiple logical operators at the same time. It is good to use parentheses around filter conditions to help make queries easy for people to read and understand.

Data warehouses often contain millions, billions, or even trillions of individual data records. Filtering data is essential to making effective use of these massive data stores.

### Sorting

When querying a database, you frequently specify the order in which you want your results to return. The ORDER BY clause is the component of a SQL query that makes sorting possible. Similar to how the WHERE clause performs, you do not have to specify the columns you are using to sort the data in the SELECT clause.

For example, suppose you want to retrieve the animal and breed for dogs over 60 pounds, with the oldest dog listed first. The following query delivers the answer:

SELECT  Animal_Name, Breed_Name

FROM   Animal

WHERE  Animal_Type = 'Dog'

AND   Weight> 60

ORDER BY Date_of_Birth ASC

If you want to return the youngest dog first, you change the ORDER BY clause as follows:

SELECT  Animal_Name, Breed_Name

FROM   Animal

WHERE  Animal_Type = 'Dog'

AND   Weight> 60

ORDER BY Date_of_Birth DESC

The ASC keyword at the end of the ORDER BY clause sorts in ascending order whereas using DESC with ORDER BY sorts in descending order. If you are sorting on multiple columns, you can use both ascending and descending as appropriate. Both the ASC and DESC keywords work across various data types, including date, alphanumeric, and numeric.

### Date Functions

* Date Columns are frequently found in OLAP environments.
* Date columns also appear in transactional systems.
* Storing date information about an event facilitates analysis across time.
* The most important thing to note is that you have to understand the database platform you are using and how that platform handles dates and times.

### Logical Functions

* Logical functions can make data substitutions when retrieving data.
* SELECT statement only retrieves data.
    
The IFF function has the following syntax:

IFF(boolean_expression, true_value, false_value)

As you can see from the syntax, the IFF function expects the following three parameters:

Boolean Expression:  The expression must return either TRUE or FALSE.
True Value:  If the Boolean expression returns TRUE, the IFF function will return this value.
False Value:  If the Boolean expression returns FALSE, the IFF function will return this value.

* IFF is just one example of a logical function. When using logical functions, you need to balance their convenience with the knowledge that you are replacing data from the database with the function's coded values. The ability to do this type of substitution is a real asset when dividing data into categories.

### Aggregate function

* Summarized data helps answer questios that executives have, and aggregate functions are an easy way to summarize data.
* Aggregate functions summarize a querys data and returns a single value.
  
Common SQL aggregate functions:

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/c5421319-6529-433a-a6be-1aa79e592ff6)

* You can also use aggregate functions to filter data.
* Aggregate functions also operate across subsets of data. For instance, you can calculate total sales by month with a single query.

### System Functions

* Each database platform offers functions tha expose data about itself.
* One of the most frequently used system functions returns the current date.
* Current date is a component of transactional records and enables time-based analysis in future.
* System functions also return data about the database environment.

### Query Optimization

* Writing an SQL query is straightforward.
* Writing a SQL query that efficiently does what you intend can be more difficult.

Factors to comsider when creating well-perfoming SQL:

* Parametrization: Whenever a SQL query executes, the database has to parse the query. Parsing translates the human-readable SQL into code the database understands. Parsing takes time and impacts how long it takes for a query to return data. Effective use of parameterization reduces the number of times the database has to parse individual queries.
  
* Indexing: A full table scan is like flipping through every page in a book to find a specific piece of data.For small tables, full table scans happen quickly. As data volumes increase, scanning the entire table takes a long time and is not efficient. To speed up query performance, you need a database index. A database index works like the index in the back of a book. Instead of looking at each page in a book to find what you are looking for, you can find a specific page number in the index and then go to that page.

A database index can point to a single column or multiple columns. When running queries on large tables, it is ideal if all of the columns you are retrieving exist in the index. If that is not feasible, you at least want the first column in your SELECT statement to be covered by an index.

If a query is running slowly, look at the indexes on the underlying tables. If you think a new index would help improve query performance, discuss it with a database administrator. The administrator will look at other factors that impact performance and will have the permissions to create an index if necessary.

While indexing improves query speed, it slows down create, update, and delete activity. An indexing strategy needs to match the type of system the database supports, be it transactional or reporting.
  
* Data Subsets and Temporary Tables:It is possible to create a temporary table to make the data more manageable. Temporary tables can store the results of a query and are disposable. Temporary tables automatically get removed when the active session ends. Using temporary tables is an effective method of creating subsets for ad hoc analysis.
  
* Execution Plan: An execution plan shows the details of how a database runs a specific query. Execution plans are extremely helpful in troubleshooting query performance issues. They provide additional information about how a query is spending its time. For example, an execution plan can tell you if a slow-running query uses a full table scan instead of an index scan. In this case, it could be that the query is poorly written and not using the existing indexes. It also could be that a column needs a new index. Looking at execution plans is an integral part of developing efficient queries. It is worth understanding the nuances of how to interpret execution plans for the database platform you use. If you need help understanding an execution plan, get in touch with your local database administrator.


# Chapter 4: Data Quality

## Data Quality Challenges

### Duplicate Data

* Duplicate data occurs when data representing the same transaction is accidentally duplicated within a system.
* Humans are resposible for creating duplicate data.
* System architects work diligently to prevent duplicate data from being created.
* The best way to resolve duplicate data is to prevent its creation in the first place.
* One common approach to stopping duplicate data before it gets into a system is a visual warning to alert the user.
* Having multiple data sources for the same data elements is also a source of duplicate data.

### Redundant Data

* Redundant happens when the same data elements exist in multiple places within a system.
* Data redundancy is a function of integrating multiple systems.
* Root cause of data redundancy is an in appropriate database design.

### Missing values 

* Missing values occur when you expect an attribute to contain data but nothing is there.
* Missing values are also known as null values.
* A null value is the absence of a value.
* To handle missing value, you first have to check for their existence.
* SQL offers functions to check for null and functions that can replace a null with a user-specified value.
* There similar functions in both Python and R.

### Invalid Data 

* Invalid data are values outside the valid range for a given attribute.
* An invalid value violate a business rule instead of having an incorrect data type.
* You have to understand the context of a system to determine whether or not a value is invalid.
* If two tables have a relationship but no foreign keys, the conditions for invalid character data exists.
* Implementing relationships appropriately reduces the likelihood of invalid character data.

### Nonparametric Data

* Nonparametric data is the data collected from categorial variables.
* Sometimes the categories indicate differentiation, and sometimes they have a rank order associated with them

### Data Outliers

* A data outlier is a value that differs significantly from other observations in a dataset.
* With outliers you need to understand why they exist and whether they are valid in a context of your analysis.
* Outliers exist regardless of data type.

### Specification Mismatch

* Specification describes the target value for a component.
* A specification mismatch occures whn an individual components characteristics are beyond the range of acceptable values.
* Specification mismatch occurs when data does not conform to its destination data type.

### Data Type Validation

* Data type validation ensures that values in a dataset have a consistent data type.
* Programming languages, including SQL, Python, and R all have data type validation function.
* Use these functions to validate the data type for each column in a data file before attempting a database load.

## Data Manipulation Techniques

### Recoding Data

* Recoding data is a technique you can use to map original values for a variable into new values to facilitate analysis.
* Recoding groups data into multiple categories, creating a categprical variable.
* A categorical variable is either nominal or ordinal.
* Nominal variable are any variable with two or more categories where there is no natural order of categories, like hair color or eye color.
* Ordinal variables are categories with an inherent rank.
* T-shirt is an example of an ordinal variable, as size come in small, medium, large, and extra large.
* Recoding is helpful when you have numeric data you want to analyze by category.

### Derived Variables

* Derived variable is a new variable resulting from a calculatio on an existing variable.

### Data Merge

* A data merge use a common variable to combine multiple database with different structures into a single dataset.
* Merging data improves the quality by adding new variables to your existing data.
* Additional variables make for a richer dataset, which positively impacts the quality of your analysis.
* ETL processes commonly append data while transforming data for use in analytical environments.
* Since a data merge adds columns to a dataset, merging gives you additional data about specific observation.

### Data Blending

* Data blending combines multiple sources of data into a single dataset at the reporting layer.
* While data blending is conceptually similar to the extract, transform, and load process, there is crucial difference.
* Recall that ETL processes operate on a schedule, copying data from source systems into analytics environments.
* Business requirements drive the scheduling, such as near real-time, hourly, daily, weekly, monthly, or manually.
* Typically, an organizations IT department designs, builds, operates, and maintains ETL processes.
* Data blending differs from ETL in that it allows an analyst to combine datasets in an ad hoc manner without the saving the blended dataset in a relational database.
* Data blending can reduce the burden on IT as it gives analysts the ability to merge data.
* ETL/ELT connects data at the database layer whereas data blending connects data at the visualization layer.

### Concantenation

* Concantenation is the merging of separate variables into a single variable.
* Concantenation is a highly effective technique when dealing with a source system that stores components of a single value in multiple columns.
* The need for concantenation frequently occurs when dealing with date and  time data.
* Concantenation is useful when generating address information.

### Data Append

* A data append combines multiple data sources with the same structure, resulting in a new dataset containing all the rows from the original dataset.
* When appending data, you save the result as new dataset for ongoing analysis.

### Imputation

* Imputation is a technique for dealing with missing values by replacing them with substitutes.
* When merging multiple data sources, you may end up with a dataset with many nulls in a given column.
* If you are collecting a sensor data, it is possible to have missing values due to collection or transmission issues.

Few approaches an analyst can use for imputing values:

* Remove Missing Data: With this approach, you can move rows with missing values without impacting the quality of your overall analysis.
* Replace with Zero: With this approach, you replace missing values with zero. Whether or not it is appropriate to replace missing data with a zero is contextual.
* Replace with Overall Average: Instead of using a zero, you can compute the average for all rows that have data and then replace missing values with the calculated average.
* Replace with Most Frequent (Mode): Alternatively, you can take the most frequently occuring values called the mode, and use it as a constant.
* Closest Value Average: With this approach, you use the values from the rows before and after the missing values.

### Reduction





