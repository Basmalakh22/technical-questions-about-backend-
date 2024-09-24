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
