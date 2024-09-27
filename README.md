# technical-questions-about-backend

technical questions , primarily focused on concepts related to programming, software development, and the Laravel framework.

## About OOP

1. [what is OOP?](#what-is-oop)
1. [what is the difference between objects and classes?](#what-is-the-difference-between-objects-and-classes)
1. [what is the difference between constructor and destructor?](#what-is-the-difference-between-constructor-and-destructor)
1. [what is the difference between trait and class?](#what-is-the-difference-between-trait-and-class)
1. [what is the difference between abstract classes and interfaces?](#what-is-the-difference-between-abstract-classes-and-interfaces)
1. [what is the difference between extend and implment?](#what-is-the-difference-between-extend-and-implment)
1. [what is the acces modefiers?](#what-is-the-acces-modefiers)
1. [what is magic methods?](#what-is-magic-methods)
1. [what is the difference between self and this?](#what-is-the-difference-between-self-and-this)
1. [what is the difference between session and cookies?](#what-is-the-difference-between-session-and-cookies)
1. [Namespace and Autoloading](#namespace-and-autoloading)

---
---

## About Database

1. [SQL ,NOSQL ,MYSQL](#sql-nosql-mysql)
1. [What is a database and relational database?](#what-is-a-database-and-relational-database)
1. [What is a primary key and foreign key?](#what-is-a-primary-key-and-foreign-key)
1. [What is the difference between a primary key and a unique key?](#what-is-the-difference-between-a-primary-key-and-a-unique-key)
1. [What is normalization and different types of it?](#what-is-normalization-and-different-types-of-it)
1. [What is a join in SQL and different types of it?](#what-is-normalization-and-different-types-of-it)
1. [What is the difference between UNION and UNION ALL?](#what-is-the-difference-between-union-and-union-all)
1. [Difference Between GROUP BY ,HAVING ,WHERE?](#difference-between-group-by-having-where)
1. [What is a transaction in SQL?](#what-is-a-transaction-in-sql)
1. [What is the difference between a clustered and a non-clustered index?](#what-is-the-difference-between-a-clustered-and-a-non-clustered-index)
1. [What is ACID in the context of database transactions?](#what-is-acid-in-the-context-of-database-transactions)
1. [What is a deadlock?](#what-is-a-deadlock)
1. [What is an ORM and when/why to use it?](#what-is-an-orm-and-whenwhy-to-use-it)
1. [Database indexing (explain/when to use/tradeoffs)?](#database-indexing-explainwhen-to-usetradeoffs)
1. [What is a database view?](#what-is-a-database-view)
1. [What is a lock and why is it useful in databases?](#what-is-a-lock-and-why-is-it-useful-in-databases)
1. [What is Elasticsearch and when to use it and explain its tradeoffs?](#what-is-elasticsearch-and-when-to-use-it-and-explain-its-tradeoffs)
1. [How can I enhancement the SQL query?](#how-can-i-enhancement-the-sql-query)
1. [What is the innodb?](#what-is-the-innodb)
1. [FUNCTION,STORED PROCEDURE,TRIGGER?](#functionstored-proceduretrigger)

---
---

## About Laravel

1. [What is the MVC?](#what-is-the-mvc)
1. [Laravel request lifecycle?](#laravel-request-lifecycle)
1. [Service Container VS Service Provider](#service-container-vs-service-provider)
1. [Facades, Dependency Injection, and Helper Functions](#facades-dependency-injection-and-helper-functions)

---
---

## what is OOP?

- Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects" which can contain data and code. Data in the form of fields (attributes or properties), and code in the form of procedures (methods).

---

## what is the difference between objects and classes?

- Class: A prototype that defines the variables and methods common to all objects of a certain kind.
- Object: An instance of a class. It contains real values instead of variables.

---

## what is the difference between constructor and destructor?

- Constructor: A method called when an object is instantiated, used to initialize the object.
- Destructor: A method called when an object is destroyed, used to clean up resources.

---

## what is the difference between trait and class?

- Class: A blueprint for creating objects with properties and methods.
- Trait: A mechanism for code reuse in single inheritance languages like PHP. Traits allow you to create reusable pieces of code.Traits are used to declare methods and abstract methods that can be used in multiple classes. and the methods can have any access modifier (public, private, or protected).

---

## what is the difference between abstract classes and interfaces?

- Abstract Class: Can have both abstract methods (without implementation) and concrete methods (with implementation). Cannot be instantiated directly.
- Interface: Can only have method declarations without implementation. A class that implements an interface must implement all of its methods.

- Abstract classes are similar to interfaces.they may contain a mix of methods declared with or without an implementation. However, with abstract classes, you can declare fields that are not static, and define public, protected, and private concrete methods. With interfaces, all fields are automatically public, static, and all methods that you declare or define are public. In addition, you can extend only one class, whether or not it is abstract, whereas you can implement any number of interfaces.

---

## what is the difference between extend and implment?

- extend: Used to inherit from a class.
- implement: Used to implement an interface.

---

## what is the acces modefiers?

- Access modifiers control the visibility of properties and methods in a class. They include:
  - public: Accessible from anywhere.
  - protected: Accessible within the class and its subclasses.
  - private: Accessible only within the class.

---

## what is magic methods?

- Magic methods in PHP are special methods that start with double underscores (__). Examples include__construct, __destruct,__get, __set,__call, etc. They allow you to define behavior for when properties or methods are accessed or invoked in a way that is not directly defined.

---

## what is the difference between self and this?

- $this: Refers to the current instance of the class.
- self:: Refers to the class itself, not an instance. It is used to access static properties and methods.

---

## what is the difference between session and cookies?

- Sessions: Store data on the server side, more secure, used for storing sensitive information.
- Cookies: Store data on the client side (browser), less secure, used for storing less sensitive information like user preferences.

---

## Namespace and Autoloading

- Namespace allows you to group related code under a specific name, improving code organization and reusability.
- Autoloading in PHP is a mechanism that automatically loads PHP classes when they are needed, without having to manually require or include them.The most common way to implement autoloading in PHP is by using Composer, the dependency manager. Composer generates an autoloader that follows the PSR-4 standard for autoloading classes.

---
---

## SQL ,NOSQL ,MYSQL

|SQL | NOSQL | MYSQL |
|:----|:----|:----|
|stands for (Structured Query Language) is a programming language specifically designed for managing and manipulating data stored in relational databases ,it is used for Retrieving data ,Inserting data, Updating data, Deleting data, Creating new databases and tables, Setting permissions on tables, procedures, and views.|stands for “Not Only SQL”, are designed to be flexible, scalable, and capable of handling large amounts of unstructured and semi-structured data. They are particularly good for working with large sets of distributed data.|is an open-source relational database management system (RDBMS) ,“MySQL” stands for “My Structured Query Language”, It is based on the structured query language (SQL), As an RDBMS, MySQL organizes data into one or more tables where data types may be related to each other. These relations help SQL perform queries and operations on the data much more efficiently.|

---

## What is a database and relational database?

- A database is an organized collection of data stored and accessed electronically. It provides a way to store, organize, and retrieve large amounts of data efficiently.

- organizes data into tables with rows and columns, where each row represents a record and each column represents a specific attribute of that record. The “relational” aspect comes from the ability to link these tables based on shared attributes or keys, allowing for efficient organization, querying, and manipulation of interconnected data.

---

## What is a primary key and foreign key?

- A database is an organized collection of data stored and accessed electronically. It provides a way to store, organize, and retrieve large amounts of data efficiently.
A primary key is a column or combination of columns that uniquely identifies each row in a table. It enforces the entity integrity rule in a relational database.

- A foreign key is a column or combination of columns that establishes a link between data in two tables. It ensures referential integrity by enforcing relationships between tables.

---

## What is the difference between a primary key and a unique key?

- A primary key is used to uniquely identify a row in a table and must have a unique value.
- unique key ensures that a column or combination of columns has a unique value but does not necessarily identify the row.

---

## What is normalization and different types of it?

- Normalization is the process of organizing data in a database to minimize redundancy and dependency. It involves breaking down a table into smaller tables and establishing relationships between them.
  - First Normal Form (1NF)
  - Second Normal Form (2NF)
  - Third Normal Form (3NF) Boyce-Codd Normal Form (BCNF) Fourth Normal Form (4NF)
  - Fifth Normal Form (5NF) or Project-Join Normal Form (PJNF)

---

## What is a join in SQL and different types of it?

- A join is an operation used to combine rows from two or more tables based on related columns.

|Inner Join | Left (Outer) Join | Right (Outer) Join | Full (Outer) Join |
|:----|:----|:----|:----|
|Returns rows when there is a match in both tables.|Returns all rows from the left table, and the matched rows from the right table; if there is no match, NULLs are used to fill in columns from the right table.|Returns all rows from the right table, and the matched rows from the left table; if there is no match, NULLs are used to fill in columns from the left table.|Returns rows when there is a match in one of the tables.|

---

## What is the difference between DELETE and TRUNCATE in SQL DROP?

|DELETE | TRUNCATE | DROP |
|:----|:----|:----|
|DML command|DDL command|DDL command|
|delete all records or specific records temporary|delete all records permanently|delete table and all records|
|table is present|table is present|table is not present|
|rollback is supported|rollback is not supported|rollback is not supported but we can restore the table by using flashback command|
|developer command|DBA command|DBA command|

---

## What is the difference between UNION and UNION ALL?

- UNION and UNION ALL are used to combine the result sets of two or more SELECT statements.

|UNION | UNION ALL|
|:----|:----|
|removes duplicate rows from the combined result set.| includes all rows, including duplicates.|

---

## Difference Between GROUP BY ,HAVING ,WHERE?

|GROUP BY| HAVING | WHERE |
|:----|:----|:----|
|Groups rows that have the same values in specified columns into summary rows.|Filters groups after grouping.|Filters rows before grouping.|

---

## What is a transaction in SQL?

- A transaction is a sequence of SQL statements that are executed as a single logical unit of work. It ensures data consistency and integrity by either committing all changes or rolling them back if an error occurs.

---

## What is the difference between a clustered and a non-clustered index?

|Clustered Index| Non-clustered Index|
|:----|:----|
|determines the physical order of data in a table. It changes the way the data is stored on disk and can be created on only one column. A table can have only one clustered index.| does not affect the physical order of data in a table. It is stored separately and contains a pointer to the actual data. A table can have multiple non-clustered indexes.|

---

## What is ACID in the context of database transactions?

- ACID stands for Atomicity, Consistency, Isolation, and Durability. It is a set of properties that guarantee reliable processing of database transactions.

|Atomicity| Consistency | Isolation | Durability|
|:----|:----|:----|:----|
|ensures that each transaction is treated as a single unit, which either succeeds completely or fails completely.|ensures that a transaction brings the database from one valid state to another.|ensures that concurrent transactions do not interfere with each other.|ensures that once a transaction is committed, its changes are permanent and survive system failures.|

---

## What is a deadlock?

- A deadlock occurs when two or more transactions are waiting for each other to release resources, resulting in a circular dependency. As a result, none of the transactions can proceed, and the system may become unresponsive.

---

## What is an ORM and when/why to use it?

- ORM (Object-Relational Mapping) is a programming technique used to convert data between incompatible type systems using object-oriented programming languages. It creates a "virtual object database" that can be used from within the programming language.
- There are several reasons to use an ORM:
  - Simpler Data Handling: Instead of writing long SQL queries, you use simple commands in your programming language to access and manipulate data.
  - Less Repetitive Code: It reduces the amount of repetitive code you need to write, like setting up connections and handling results.
  - Easy Database Switching: ORMs allow you to change the database type (e.g., from MySQL to PostgreSQL) without changing much in your code.
  - Cleaner Code: It keeps your code clean and organized, which makes it easier to maintain and ensures data is handled correctly.

---

## Database indexing (explain/when to use/tradeoffs)?

- Database indexing is a data structure technique used to quickly locate and access the data in a database table.
Indexes are used to speed up the retrieval of data but can also lead to slower writes and increased storage use.
  - When to use: Indexing should be considered when the performance of SELECT queries needs to be improved, particularly on large datasets, or when specific data needs to be accessed frequently.
  - Tradeoffs: While indexes significantly improve query speed, they also require additional disk space and can slow down data insertion, updates, and deletions because each transaction requires the index to be updated.

---

## What is a database view?

- A database view is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database. Views can aggregate data from various tables and present it as if it were coming from a single table, thereby providing a simplified and secure method of querying data.
  - ex. local Partitioned view,Partitioned view ,Indexed view

---

## What is a lock and why is it useful in databases?

- A lock in a database is a way to control access to data, ensuring that only one person or process can read or change specific data at a time.
It’s useful because:

1. Prevents conflicts: Stops two people from changing the same data at the same time, avoiding errors.
2. Keeps data accurate: Ensures data stays correct by controlling how it’s accessed.
3. Protects ongoing work: Makes sure that one process finishes its task before another starts.

---

## What is Elasticsearch and when to use it and explain its tradeoffs?

- Elasticsearch is a powerful search and analytics engine built on top of Apache Lucene, used to store, search, and analyze big volumes of data quickly. It’s widely used for full-text search, data logging, and monitoring systems.
  - used in Full-Text Search,Real-Time Data , Complex Queries ,Data Aggregation
  - designed for horizontal scalability, reliability, and easy management
  - cons =>Complex Setup,Resource-Intensive ,Data Consistency,Not for Small Data

---

## How can I enhancement the SQL query?

1. Use Indexes: Make sure the columns you're filtering (WHERE), joining (JOIN), or sorting (ORDER BY) are indexed for faster
queries.
2. Select Only What You Need: Instead of SELECT *, choose only
the columns you need, e.g., SELECT name, age FROM users.
3. Limit Results: If you don’t need all rows, use LIMIT to get only a
certain number, like LIMIT 10.
4. Simplify Joins: Try to minimize how many tables you're joining
unless it's necessary, as too many JOINs slow things down.
5. Use Aliases: Give your tables short names to make the query easier to read, like SELECT u.name FROM users u.

---

## What is the innodb?

- InnoDB is a storage engine for MySQL, designed to provide high reliability and performance when processing large data volumes. It supports ACID- compliant transactions, foreign keys, and row-level locking. InnoDB is the default storage engine for MySQL and is recommended for applications that require frequent read and write operations, require transaction support, and maintain full data integrity.

---

## FUNCTION,STORED PROCEDURE,TRIGGER?

| |Function| STORED PROCEDURE | TRIGGER |
|:----|:----|:----|:----|
|Purpose| Does one task and returns a single result.|Can do multiple tasks, like inserting, updating, or deleting data.|Automatically runs when something happens in the database (like adding, updating, or deleting data).|
|Use | You can use it inside a query, like SELECT.|  You call it to run, but can't use it directly in a SELECT.| You don't call it directly. It activates by itself when a specific event occurs.|
|Changes | It doesn't change the database, just calculates and returns data.| Can change data in the database and handle complex processes.|Can be used to modify, validate, or log changes automatically when certain actions happen in the database.|

---
---

## What is the MVC?

- MVC (Model-View-Controller) is a design pattern helps keep the application organized by separating the data (Model), user interface (View), and application logic (Controller).

|Model |View |Controller|
|:----|:----|:----|
|Handles data and business logic.|Displays data to the user and handles the presentation layer.|Manages communication between the Model and the View.|
|Interacts with the database to retrieve and manipulate data.|Contains the HTML, CSS, and JavaScript code that users interact with.|Receives input from the user (through HTTP requests), processes it using the Model, and returns the appropriate View.|
|Example in Laravel: Eloquent ORM is used to interact with database tables.|Example in Laravel: Blade templates are used for views.|Example in Laravel: Controllers are created to handle the business logic and determine which data is passed to the View.|

---

## Laravel request lifecycle?

- The Laravel lifecycle starts when a server receives a request and directs it to the public/index.php file, which acts as the entry point. Laravel then loads the necessary framework components via service providers. The request passes through global and route-specific middleware before reaching the router. The router dispatches the request to the appropriate controller or closure, which generates a response. The response travels back through the middleware for any post-processing, and is then sent to the user.

---

## Service Container VS Service Provider

| Service Container| Service Provider|
|:----|:----|
|is essentially a registry or a container that manages class dependencies and resolves them. It’s a powerful tool for performing dependency injection, where you can bind classes or interfaces and resolve them whenever needed.|is a mechanism to register services (including bindings to the Service Container) and configure how these services should be used by Laravel. Service providers are where you tell Laravel what to bind into the service container.|

---

## Facades, Dependency Injection, and Helper Functions

| |Facades| Dependency Injection | Helper Functions|
|:----|:----|:----|:----|
|What it is|A shortcut to use Laravel services without manually creating objects.|Laravel automatically gives your class the objects (dependencies) it needs.|Simple functions that help with common tasks, like working with URLs or strings.|
|Example| Instead of creating a cache object, you just use Cache::put(). |If your class needs a UserRepository, Laravel injects it for you.|url('home') generates a URL for you.|
|Good for| Quick and easy access to services.| Keeping your code clean and easy to test.|Quick, one-line tasks.|
|Downside| Can make testing and understanding your code a bit harder.|Requires a bit more setup compared to Facades.| If overused, it can make your code harder to manage.|
