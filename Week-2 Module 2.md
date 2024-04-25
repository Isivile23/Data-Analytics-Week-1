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

* Reduction is the process of shrinking an extensive dataset without negatively impacting its analytical value.
* Selectiong a method depends on the types of data you have and what you are trying to analyze.
* Dimensionality reduction and numerosity reduction are two techniques for data reduction.

#### Dimensionality Reduction

* One reduction technique is dimensionality reduction, which removes attributes from a dataset.
* Removing attributes reduces the datasets overall size.
* You can use any programming language, including Python or R, to remove dimensions.

 #### Numerosity Reduction

 * Numerosity reduction reduces the overall volume of data.
 * As data volume grows, numerosity reduction can improve efficiency of your analysis.
 * One way to reduce the volume of quantitative data is by creating histogram.
 * A histogram is a diagram made up of rectangles, or bars, that show how frequently a specific value occurs.
 * Another approach of reducing the data is through sampling.
 * Sampling is a technique that selects a subset of individual records from the initial dataset.

##### Aggregation

* Data aggregation is the summarization of raw data for analysis.
* When dealing with billions of individual records, a data summary can help you make sense of t all.
* Aggregating data provides answers that help make decisions.
* Aggregation is also a means of controlling privacy.

##### Transposition

* Transposition data is when you want to turn rows into columns or columns into rows to facilitate analysis.
* Combining aggregation with transposition is a powerful data manipulation technique.

##### Normalization

* Normalization data converts data from different scales to the same scale.
* After normalization is complete the data is ready for statistical analysis.

##### Min-Max Normalization

* Min-max Normalization is one of the most straightforward approaches for mormalizing data.

#### Parsing/String Manipulation

* Raw data can contain columns with composite or distributed structural issues.
* A composite issue is when a raw data source has multiple, distinct values combined within a single character column.
* When this happens, each value in a composite column has data that represents more than one attribute.
* Composite columns need to be split into their component parts to aid analysis.
* Distributed issue is when data in a single column spreads across multiple columns.
* When that happens you need to combine the individual columns.
* Whenever you have composite or distributed structural data issues, you need to manipulate the strings before starting the analysis.
* You need to manipulate string data to improve data quality.

## Managing Data Quality

### Circumstances to Check for Quality

* Data Acqusition
* Data Transformation and Conversion
* Data Manipulation
* Final Product Preparation

### Automated Validation

* One way to prevent data entry mistakes from adversley impacting data quality is to automate data validation checks.
* Before automatically validating input data, you need to understand how source data fields map to their corresponding database column.
* When mapping input data, pay close attention to the data types in databases.

### Data Quality Dimension

* It is essential to consider multiple attributes of data when considering its quality.
* Six dimensions to take into account when assessing data quality are, accuracy, completeness, consistency, timeliness, uniqueness, and validity.

### Data Quality Rules and Metrics

### Methods to Validate Quality

#### Reasonable Expectation

* One approach is to determine whether or not the data in your analytics environment meets your reasonable expectation.
* After defining how you want to measure your expectations check by creating exception reports as part of your ETL processes.

#### Data Profiling

* Another approach to improving quality is to profile your data.
* Data profiling uses statistical measures to check for data discrepancies, including values that are missing, that occur either infrequently or too frequently, or that should be eliminated..
* Profiling can also identify irregular patterns within your data.

#### Data Audits

* Data audits look at your data and help you understand whether or not you have the data you need to operate your business.
* Data audits use data profiling techniques and can help identify data intergrity and security issues.

#### Sampling

* Another method for validating data quality is by examining a sample of your data.
* Sampling is a statistical tecnique in which you use a subset of your data to inform conclusions about your overall data.

#### Cross-Validation

* Analysts frequently use existing data to generate predictive models using a variety of statistical methods.
* Cross validation is statistical technique that evaluates how well predictive models perform.
* Cross-validation works by dividing data into two subsets.
* The first subset is the training set, and the second is the testing, or validation set.
* You use data from training set to build a predictive model.
* You then cross-validate the model using the testing subset to determine how accurate the predition is.
* Cross-validation is also helpful in identifying data sampling issues.

# Chapter 5: Data Analysis and Statistics

## Fundamentals of Statisctics

* One key concept is the definition of a population. A population represents all the data subjects you want to analyze.
* Collecting a sample is a cost-effective and time-effective alternative to gathering census data.
* A sample is a subset of the population.
* A variable is a unique attribute of a data subject.
* Univariate analysis is when you explore the characteristics of a single variable, independent of the rest of the dataset.
*  An observation is an individual record in a dataset corresponding to a tabular data row.

### Common Symbols in Statistics

* Statistics is all about exploring numbers and performing calculations.
* People use emojis when texting to symbolize emotions. Similarly, statisticians use symbols to convey meaning.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/656bd9ed-c381-4877-8de7-dba2a574acac)

## Descriptive Statistics

* Descriptive statistics is a branch of statistics that summarizes and describes data.
* As you explore a new dataset for the first time, you want to develop an initial understanding of the size and shape of the data.
*  You use descriptive statistics as measures to help you understand the characteristics of your dataset.
* You also use descriptive measures to develop summary information about all of a variable's observations.

### Measures of Frequency 

* Measures of frequency help you understand how often something happens.
* When encountering a dataset for the first time, you want to determine how much data you are working with to help guide your analysis.

#### Count

* The most straightforward way to understand how much data you're working with is to count the number of observations.
* Understanding the total number of observations is a frequently performed task.
* As such, there is a count function in everything from spreadsheets to programming languages.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/a0347db4-6362-4692-9e79-a8676058cab4)

#### Percentage

* The percentage is a frequency measure that identifies the proportion of a given value for a variable with respect to the total number of rows in the dataset.
* To calculate a percentage, you need the total number of observations and the total number of observations for a specific value of a variable.


![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/665dd7af-e283-4172-a4a6-3d083aec5577)

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/e8b15b65-37df-4f58-a207-c4a56a3c1305)

* Knowing that 51 percent of the sample is female helps you understand that the balance between males and females is pretty even.

#### Frequency

* Frequency describes how often a specific value for a variable occurs in a dataset. You typically explore frequency when conducting univariate analysis.

  ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/43d24915-7d4f-401f-8e46-01dc2c5bcfd4)

### Measures of Central Tendency

* To help establish an overall perspective on a given dataset, an analyst explores various measures of central tendency.
*  You use measures of central tendency to identify the central, or most typical, value in a dataset.
*  There are numerous ways to measure central tendency, and you end up using them in conjunction with each other to understand the shape of your data.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/2c592433-3971-4b24-ab9c-1470412e22bf)

* The mean, or average, is a measurement of central tendency that computes the arithmetic average for a given set of numeric values.
* To calculate the mean, you take the sum of all values for an observation and divide by the number of observations.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/262f3fe2-467c-4218-87d0-5270288c49a6)

* Although the formula for calculating the sample mean looks slightly different, the process is the same. You sum all sample observations for a variable and then divide by the number of observations:

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/dcef51b8-7108-435f-b180-5d8466204298)

* Data analysis tools, including spreadsheets, programming languages, and visualization tools, all have functions that calculate the mean.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/93c44fdb-ef7f-4a06-a80c-fdb528730560)

* Another measurement of central tendency is the median, which identifies the midpoint value for all observations of a variable.
* The first step to calculating the median is sorting your data numerically.
* Once you have an ordered list of values, the next step depends on whether you have an even or an odd number of observations for a variable.

 ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/0ccb1254-b585-4a33-8eac-96534c5290a2)

* The mode is a variable's most frequently occurring observation. Depending on your data, you may not have a mode.

### Measures of Dispersion

* In addition to central tendency, it is crucial to understand the spread of your data. You use measures of dispersion to create context around data spread. Let's explore five common measures of dispersion.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/74ba34ea-4c2c-46ba-8d1a-d94c149ab909)

* The range of a variable is the difference between its maximum and minimum values.
* Understanding the range helps put the data you are looking at into context and can help you determine what to do with outlier values.
* It can also identify invalid values in your data.
* Spreadsheets and programming languages have functions available to identify minimum and maximum values.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/ab82276d-5e86-44e3-9995-6d0af81ba8ae)

* In statistics, a probability distribution, or distribution, is a function that illustrates probable values for a variable, and the frequency with which they occur.
* Histograms are an effective tool to visualize a distribution, because the shape provides additional insight into your data and how to proceed with analysis.
* Distributions have many possible shapes, including normal, skewed, and bimodal.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/e052e78c-0177-4ef9-9c31-b06c20ae1495)

* The normal distribution is symmetrically dispersed around its mean, which gives it a distinctive bell-like shape.
* Due to its shape, the normal distribution is also known as a “bell curve".

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/d522b6e1-8d31-4c6b-9ad2-9a7810839943)

* A skewed distribution has an asymmetrical shape, with a single peak and a long tail on one side. Skewed distributions have either a right (positive) or left (negative) skew.
* When the skew is to the right, the mean is typically greater than the median. On the other hand, a distribution with a left skew typically has a mean less than the median.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/de14de77-c653-4f85-b8a4-b48c0969ac04)

* A bimodal distribution has two distinct modes, whereas a multimodal distribution has multiple distinct modes. When you visualize a bimodal distribution, you see two separate peaks.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/b9d04894-c1a7-4730-b5c6-07ec2daf54cf)

* Variance is a measure of dispersion that takes the values for each observation in a dataset and calculates how far away they are from the mean value. This dispersion measure indicates how spread out the data is in squared units. Mathematically,  signifies population variance, which you calculate by taking the average squared deviation of each value from the mean, as follows:

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/d46fbef9-8b52-48e8-9b38-60d222d5758f)

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/2d579020-1d35-49b9-9125-805a3f753118)

* Standard deviation is a statistic that measures dispersion in terms of how far values of a variable are from its mean. Specifically, standard deviation is the average deviation between individual values and the mean.
* Mathematically,  signifies population standard deviation, which you calculate by taking the square root of the variance, as follows:

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/f0d1c524-2863-4165-8caa-5cb6654d326d)

### Each Sample is Unique

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/60f6284d-ccfa-4de1-a320-fbb3fb72a8aa)

*The Central Limit Theorem and empirical rule combine to make the normal distribution the most important distribution in statistics. There are two special normal distributions that have broad applicability and warrant a deeper understanding.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/7ed8859b-a9e6-4a37-9366-30c010585274)

* The standard normal distribution, or Z-distribution, is a special normal distribution with a mean of 0 and a standard deviation of 1. You can standardize any normal distribution by converting its values into Z-scores. Converting to the standard normal lets you compare normal distributions with different means and standard deviations.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/9d038cf3-dd77-442b-9196-97eb405607b9)

*The Student's t-distribution, commonly known as the t-distribution, is similar to the standard normal distribution in that it has a mean of 0 with a bell-like shape. One way the t-distribution differs from the standard normal distribution is how thick the tails are since you can use the t-distribution for sample sizes of less than 30. 

### Measures of Position

* Understanding a specific value for a variable relative to the other values for that variable gives you an indication of the organization of your data.
* Statisticians commonly use quartiles to describe a specific observation's position.
* The process of obtaining quartiles is similar to that of determining the median. You first sort a numeric dataset from smallest to largest and divide it positionally into four equal groups. Each grouping is known as a quartile.
* The first quartile is the group that starts with the minimum value, whereas the fourth quartile is the group that ends with the maximum value.

## Inferential Statistics

* Inferential statistics is a branch of statistics that uses sample data to draw conclusions about the overall population.

### Confidence Intervals

* Each time you take a sample from a population, the statistics you generate are unique to the sample.
* In order to make inferences about the population as a whole, you need a way to come up with a range of scores that you can use to describe the population as a whole.
* A confidence interval describes the possibility that a sample statistic contains the true population parameter in a range of values around the mean.
* When calculating a confidence interval, you end up with a lower bound value and an upper bound value. Given the confidence interval range, the lower bound is the lower limit, and the upper bound is the upper limit.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/2a4d9920-42d2-43d0-b171-4bb00e9dfe86)

* While it is possible to develop a confidence interval for a skewed distribution, our conversation will focus on a normal distribution and presume the sample mean, population standard deviation, and sample size are known.
* When calculating a confidence interval, you need to specify the confidence level in addition to the sample mean, population standard deviation, and sample size.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/6f84c2dc-822d-4709-b90f-e0ed00172800)

* When calculating confidence intervals, you need to have the standard deviation of the entire population. However, since getting measures about the whole population is challenging, the population standard deviation is likely unknown. In that case, while it's more precise to use the t-distribution, if your sample size is greater than 30, it's reasonable to use the normal distribution and substitute the sample standard deviation as follows:

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/7b517ca5-e361-438c-877d-e13bbdd8718e)

### Hypothesis Testing
* Data analysts frequently need to build convincing arguments using data. One of the approaches to proving or disproving ideas is hypothesis testing. A hypothesis test consists of two statements, only one of which can be true. It uses statistical analysis of observable data to determine which of the two statements is most likely to be true.
* A hypothesis test consists of two components: the null hypothesis and the alternative hypothesis.
*  A null hypothesis (H0) presumes that there is no effect on the test you are conducting.
*  When hypothesis testing, your default assumption is that the null hypothesis is valid and that you have to have evidence to reject it.
*  The alternative hypothesis (Ha) presumes that the test you are conducting has an effect. The alternative hypothesis for the airline pricing example is that people over 75 inches are willing to pay more for more legroom. The ultimate goal is to assess whether the null hypothesis is valid or if there is a statistically significant reason to reject the null hypothesis.
*  To determine the statistical significance of whether to accept or reject the null hypothesis, you need to compare a test statistic against a critical value.
*  A test statistic is a single numeric value that describes how closely your sample data matches the distribution of data under the null hypothesis.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/5d1a45b8-6d78-4e7b-b35e-b29a2bc53484)

* Hypothesis testing with the Z-test is appropriate when you have a sample size over 30 and a known population standard deviation, and you are using the normal distribution.

  ![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/08bcf346-3f6f-4d31-8ee9-04a8995f2096)

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/0e6ed64c-7669-465a-b81e-3383d9b65b22)

* Frequently, the standard deviation of the population is unknown. It's also possible that you will have a sample size of less than 30. In either of those cases, the Z-test is not an option. In this case, you can perform a t-test. A t-test is conceptually similar to a Z-test, but uses the t-distribution instead of the standard normal distribution. You interpret the results of a t-test the same way you interpret a Z-test in terms of critical regions, confidence levels, and p-values.

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/cc4bc2de-07b9-4d54-9244-0e4627a69a83)

![image](https://github.com/Isivile23/Data-Analytics-Week-1/assets/162969923/4b7c469c-412f-4f17-8a91-82be8ea8cbe7)

* Z-tests and t-tests work well for numeric data. However, there are times when you want to compare the observed frequencies of categorical variables against what was expected. The chi-square test is available when you need to assess the association of two categorical variables. In this case, the null hypothesis asserts that there is no association between the variables, and the alternative hypothesis states that there is an association between them.

### Simple Linear Regression

* Simple linear regression is an analysis technique that explores the relationship between an independent variable and a dependent variable.
* You can use linear regression to identify whether the independent variable is a good predictor of the dependent variable. You can perform a regression analysis in spreadsheets like Microsoft Excel and programming languages, including Python and R.
* When plotting the results of a regression, the independent variable is on the x-axis and the dependent variable is on the y-axis.
* Simple linear regression has many applications. For example, you might use simple linear regression to assess the impact of a marketing promotion on a company's sales. In healthcare, you might explore the relationship between a person's age and body mass index (BMI).

### From Simple to Multiple Linear Regression

* Note that you explore the relationship between two variables using simple linear regression. Multiple linear regression builds on that concept by examining the effect of numerous independent variables on a dependent variable.
* A crucial aspect of linear regression is the correlation between how far the observations are from the regression line. Correlation is a measurement of how well the regression line fits the observations. The correlation coefficient (r) ranges between –1 and 1 and indicates the strength of the correlation. The stronger the correlation, the more tightly the points wind around the line of best fit. Perfect correlation is when r has a value of either –1 or 1, implying that every data point falls directly on the regression line. Interpreting correlation strength depends on the industry.

## Analysis Techniques

### Determine Type of Analysis

* When embarking on a new analytics challenge, you need to understand the business objectives and desired outcomes. This understanding informs the type of analysis you will conduct. The first step to understanding the objectives is to ensure that you have clarity on the business questions at hand. Recall that the goal of answering a business question is to develop an insight that informs a business decision.

### Types of Analysis

### Exploratory Data Analysis

At the onset of your analysis, you will encounter many datasets for the first time. When first exploring a dataset, it's a good idea to perform an exploratory data analysis. An exploratory data analysis (EDA) uses descriptive statistics to summarize the main characteristics of a dataset, identify outliers, and give you context for further analysis. 

While there are many approaches to conducting an EDA, they typically encompass the following steps:

* Check Data Structure:  Ensure that data is in the correct format for analysis. Most analysis tools expect data to be in a tabular format, so you need to confirm that your data has defined rows and columns.
  
* Check Data Representation:  Become familiar with the data. In this step, you validate data types and ensure that variables contain the data you expect.
  
* Check if Data Is Missing:  Check to see if any data is missing from the dataset and determine what to do next. While checking for null values, calculate the proportion of each variable that is missing. If you discover that most of the data you need is missing, you need to either categorize it as missing or impute a value for the missing data. You can also go back to the source and remediate any data extraction issues.
  
* Identify Outliers:  Recall from Chapter 4 that an outlier is an observation of a variable that deviates significantly from other observations of that variable. As shown in this chapter, outliers can dramatically impact some descriptive statistics, like the mean. It would be best to determine the cause of outliers and consider whether you want to leave them in the data before proceeding with any ongoing analysis.
  
* Summarize Statistics:  Calculate summary statistics for each variable. For numeric variables, examples of summary statistics include mean, median, and variance. For categorical data like eye colour, you could develop a table showing the frequency with which each observation occurs.
  
* Check Assumptions:  Depending on the statistical method you are using, you need to understand the shape of the data. For example, if you are working with numeric data, you should choose a normal or t-distribution for drawing inferences. If you are working with categorical data, use the chi-square distribution.

# Chapter 6: Data Analytics Tools

## Spreadsheets

* The spreadsheet is the most widely used tool in the world of analytics.
* It is hard to imagine anyone who does not use spreadsheets as part of their work because they provide an intuitive way to organize our data into rows and columns.
* Spreadsheet software is installed on pretty much every computer in the modern work environment, and web-based spreadsheets are freely available to anyone.
* Spreadsheets are productivity software packages that allow users to create documents that organize any type of data into rows and columns.
* Users may place any data they like in the spreadsheet and then quickly and easily perform mathematical calculations, such as finding the sum of the values in a row or searching out the minimum, maximum, mean, and median values in a dataset.
* Spreadsheets lack any of the constraints of a relational database.
* While you can certainly organize data in a spreadsheet, there's no requirement that you do so.
* If you'd like, you can mix numbers, text, dates, and other data elements all in the same column. That does, of course, reduce the usefulness of the spreadsheet, but the user of spreadsheet software has total flexibility in how they organize their data.

### Microsoft Excel

* Microsoft Excel is the most commonly used desktop spreadsheet application. It is available as a component of the widely deployed Microsoft Office productivity suite and most modern knowledge workers have access to it.
* As with any spreadsheet, you can store data of any kind in an Excel spreadsheet.

## Programming Languages

* Programming languages allow skilled software developers to write their own instructions to the computer, allowing them to directly specify the actions that should take place during the analytics process.

### R

* The R programming language is extremely popular among data analysts because it is focused on creating analytics applications. R originally appeared in the 1990s as a statistical programming language that was popular among a niche audience. More than two decades later, the language has evolved into one of the most popular languages used by statisticians, data scientists, and business analysts around the world.
* R gained rapid traction as a popular language for several reasons. First, it is available to everyone as a free, open-source language developed by a community of committed developers. This approach broke the mold of past approaches to analytic tools that relied on proprietary, commercial software that was often out of the financial reach of many individuals and organizations.
* R also continues to grow in popularity because of its adoption by the creators of machine learning methods. Almost any new machine learning technique created today quickly becomes available to R users in a redistributable package, offered as open-source code on the Comprehensive R Archive Network (CRAN), a worldwide repository of popular R code.
* One of the most important advances in the R language was the creation of a set of R packages known as the tidyverse by Hadley Wickham and other developers. The tidyverse approach to data analysis simplifies the use of the language and makes it accessible to anyone willing to invest a few hours in learning some basic syntax.

### Python

* Python is arguably the most popular programming language in use today.
* Python is about the same age as R, but the major difference between Python and R is that Python is a general-purpose programming language.
* This means that it is capable of creating software to meet just about any need you might imagine.
* You can do everything from code a video game to perform a complex data analysis in Python.
* With that flexibility, however, comes some complexity. While R is quite popular because of its ease of use, writing software in Python requires some more expertise. Python developers usually have a more formal background in computer science and are familiar with many coding concepts, such as looping and branching, that aren't necessary in most R code.
* Python also has specialized libraries that focus on the needs of analysts and data scientists.
* In particular, the Python Data Analysis Library (pandas) provides a set of tools for structuring and analyzing data.

### Structured Query Language (SQL)

* The Structured Query Language (SQL) is the language of databases.
* Any time a developer, administrator, or end user interacts with a database, that interaction happens through the use of a SQL command.
* SQL is divided into two major sublanguages:
   * The Data Definition Language (DDL) is used mainly by developers and administrators. It's used to define the structure of the database itself. It doesn't work with the data inside a database, but it sets the ground rules for the database to function.
   * The Data Manipulation Language (DML) is the subset of SQL commands that are used to work with the data inside of a database. They do not change the database structure, but they add, remove, and change the data inside a database

* There are three DDL commands that you should know:
* The CREATE command is used to create a new table within your database or a new database on your server.
* The ALTER command is used to change the structure of a table that you've already created. If you want to modify your database or table, the ALTER command lets you make those modifications.
* The DROP command deletes an entire table or database from your server. It's definitely a command that you'll want to use with caution!

* There are also four DML commands that you should know:
* The SELECT command is used to retrieve information from a database. It is the most commonly used command in SQL as it is used to pose queries to the database and retrieve the data that you're interested in working with.
* The INSERT command is used to add new records to a database table. If you are adding a new employee, customer order, or marketing activity, the INSERT command allows you to add one or more rows to your database.
* The UPDATE command is used to modify rows in the database. If you need to change something that is already stored in your database, the UPDATE command will do that.
* The DELETE command is used to delete rows from a database table. Don't confuse this command with the DROP command. The DROP command deletes an entire database table, whereas the DELETE command just deletes certain rows from the table.

## Statistic Packages

### IBM SPSS

* One of the most popular pieces of statistical software is IBM's SPSS package.
* SPSS is one of the oldest statistical software packages, first released in 1968, but it continues to be used today by many statisticians.

### Stata

* Stata is yet another statistical analysis package that dates back to the 1980s and continues to be updated today.
* It offers essentially the same features as SPSS and SAS and provides users with both a graphical interface and a command-line interface depending on their personal preference.
* Stata is less widely used than the more popular SAS and SPSS tools.

### Minitab

* The final statistical software package covered on the Data+ exam is Minitab.
* And, once again, Minitab shares most of the same features as SPSS, SAS, and Stata but fits into the same category as Stata - an older tool that is not widely used today. 

## Machine Learning


  
