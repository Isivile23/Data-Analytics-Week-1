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

* Moving on from statistics-focused tools, the industry also makes use of a set of graphical tools designed to help analysts build machine learning models without requiring them to actually write the code to do so.
* These machine-learning tools aim to make machine-learning techniques more accessible. Analysts may still tune the parameters of their models but do not necessarily need to write scripts to do so.

### IBM SPSS Modeler 

* IBM's SPSS Modeler is one popular tool for building graphical machine learning models.
* Instead of requiring that users write code, it provides an intuitive interface where analysts can select the tasks that they would like the software to carry out and then connect them in a flowchart-style interface.

### RapidMiner

* RapidMiner is another graphical machine learning tool that works in a manner similar to IBM SPSS Modeler.
* It offers access to hundreds of different algorithms that may be placed in a visually designed machine-learning workflow.

## Analytics Suite 

### IBM Cognos

IBM Cognos is an example of one of these integrated analytics suites.  It uses a web-based platform to offer analysts within an organization access to their data and is backed by IBM's Watson artificial intelligence capability. 

The major components of Cognos include the following:

* Cognos Connection is a web-based portal that offers access to other elements of the Cognos suite.
* Query Studio provides access to data querying and basic reporting tools.
* Report Studio offers advanced report design tools for complex reporting needs.
* Analysis Studio enables advanced modeling and analytics on large datasets.
* Event Studio provides real-time data monitoring and alerting, allowing business leaders to be immediately notified when certain events take place and/or provide automated responses to those events.
* Metric Studio offers the ability to create scorecards for business leaders to quickly analyze key metrics from across the organization.
* Cognos Viewer allows stakeholders to easily interact with data and analyses prepared using Cognos.

### Microsoft Power BI

Power BI is Microsoft's analytics suite built on the company's popular SQL Server database platform.
Power BI is popular among organizations that make widespread use of other Microsoft software because of its easy integration with those packages and cost-effective bundling within an organization's Microsoft enterprise license agreement.

The major components of Power BI include the following:

* Power BI Desktop is a Windows application for data analysts, allowing them to interact with data and publish reports for others.
* The Power BI service is Microsoft's software-as-a-service (SaaS) offering that hosts Power BI capabilities in the cloud for customers to access.
* Mobile apps for Power BI provide users of iOS, Android, and Windows devices with access to Power BI capabilities.
* Power BI Report Builder allows developers to create paginated reports that are designed for printing, email, and other distribution methods.
* Power BI Report Server offers organizations the ability to host their own Power BI environment on internal servers for stakeholders to access.

### MicroStrategy

* MicroStrategy is an analytics suite that is less well-known than similar tools from IBM and Microsoft, but it does have a well-established user base.
* MicroStrategy offers many of the same tools as its counterparts, making it easy for users to build dashboards and reports and apply machine learning techniques to their business data.

### Domo

* Domo is a software-as-a-service (SaaS) analytics platform that allows businesses to ingest their data and apply a variety of analytic and modeling capabilities.
* It is not a very widely used tool, but knowledge of it is included in the objectives for the Data+ exam.

### Datorama

* Salesforce Datorama is an analytics tool that focuses on a specific component of an organization's business: sales and marketing.
* It's not a general-purpose analytics tool but is instead focused on applying machine learning, visualization, and other analytics techniques to the sales and marketing process.

### AWS QuickSight

* AWS QuickSight is a dashboarding tool available as part of the Amazon Web Services cloud offering.
* This tool's power comes from the fact that it is available on a pay-as-you-go basis and its integration with the powerful data storage, data warehousing, machine learning, and artificial intelligence capabilities offered by the Amazon cloud.

### Tableau

* Tableau is arguably the most popular data visualization tool available in the market today.
* The focus of this tool is on the easy ingestion of data from a wide variety of sources and powerful visualization capabilities that allow analysts and business leaders to quickly identify trends in their data and drill down into specific details.

### Qlik

* Qlik is another popular SaaS analytics platform, offering access to cloud-based analytics capabilities.
The major products offered by Qlik include the following:

* QlikView is the company's original analytics platform that focuses on providing rapid insights.
* Qlik Sense is a more advanced platform providing more sophisticated analytics capabilities (at a higher cost, of course!).

### BusinessObjects

* BusinessObjects is an enterprise reporting tool from SAP that is designed to provide a comprehensive reporting and analytics environment for organizations.
* One of the strengths of this suite is the ability to integrate BusinessObjects reports with other applications, allowing organizations to integrate analytics into other portions of their workflow.

