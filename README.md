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

1. [SQL ,NOSQL ,MYSQL](#sql-nosql-mysql)
1. [What is adatabase?](#what-is-adatabase)
1. [What is relational database?](#what-is-relational-database)
1. [What is a primary key?](#what-is-a-primary-key)
1. [What is a foreign key?](#what-is-a-foreign-key)
1. [What is the difference between a primary key and a unique key?](#what-is-the-difference-between-a-primary-key-and-a-unique-key)
1. [What is normalization and different types of it?](#what-is-normalization-and-different-types-of-it)
1. [What is a join in SQL and different types of it?](#what-is-normalization-and-different-types-of-it)

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

## What is adatabase?

- A database is an organized collection of data stored and accessed electronically. It provides a way to store, organize, and retrieve large amounts of data efficiently.

---

## What is relational database?

- organizes data into tables with rows and columns, where each row represents a record and each column represents a specific attribute of that record. The “relational” aspect comes from the ability to link these tables based on shared attributes or keys, allowing for efficient organization, querying, and manipulation of interconnected data.

---

## What is a primary key?

- A database is an organized collection of data stored and accessed electronically. It provides a way to store, organize, and retrieve large amounts of data efficiently.
A primary key is a column or combination of columns that uniquely identifies each row in a table. It enforces the entity integrity rule in a relational database.

---

## What is a foreign key?

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
|Inner Join|Left (Outer) Join|Right (Outer) Join|Full (Outer) Join|
|:----|:----|:----|
|Returns rows when there is a match in both tables.|Returns all rows from the left table, and the matched rows from the right table; if there is no match, NULLs are used to fill in columns from the right table.|Returns all rows from the right table, and the matched rows from the left table; if there is no match, NULLs are used to fill in columns from the left table.|Returns rows when there is a match in one of the tables.|

---

## What is the difference between DELETE and TRUNCATE in SQL DROP?

|DELETE | TRUNCATE | DROP |
|:----|:----|:----|
|DML command|DDL command|DDL command|
|elete all records or specific records temporary|delete all records permanently|delete table and all records|
|table is present|table is present|table is not present|
|rollback is supported|rollback is not supported|rollback is not supported but we can restore the table by using flashback command|
|developer command|DBA command|DBA command|