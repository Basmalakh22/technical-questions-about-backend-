# About Laravel

1. [What is the MVC?](#what-is-the-mvc)
1. [Laravel request lifecycle?](#laravel-request-lifecycle)
1. [Service Container VS Service Provider](#service-container-vs-service-provider)
1. [Facades, Dependency Injection, and Helper Functions](#facades-dependency-injection-and-helper-functions)
1. [GET route vs POST route](#get-route-vs-post-route)
1. [Route::resource vs Route::controller](#routeresource-vs-routecontroller)
1. [views and Blade templates](#views-and-blade-templates)
1. [Using migrations and the Eloquent ORM in Laravel instead of over directly dealing with the database using raw SQL.](#using-migrations-and-the-eloquent-orm-in-laravel-instead-of-over-directly-dealing-with-the-database-using-raw-sql)

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

---

## GET route vs POST route

| |GET route | POST route|
|:----|:----|:----|
|Purpose| used to retrieve data from the server. fetching information without modifying any data. |used to send data to the server.creating or updating resources, like submitting a form.|
|Characteristics| Data is passed via the URL.Less secure |Data is sent in the body of the HTTP request (not visible in the URL).More secure|
| |GET is for retrieving data.|POST is for sending or modifying data.|

---

## Route::resource vs Route::controller

| |Route::resource | Route::controller|
|:----|:----|:----|
|Purpose |specifically designed to create a set of RESTful routes that correspond to typical CRUD operations (Create, Read, Update, Delete) for a resource.|is used to define a route to a single controller with multiple action methods based on the URI segments.|
|Functionality|Automatically generates multiple routes based on resourceful conventions.|Routes are defined with a more manual approach; it maps URIs directly to controller methods based on naming conventions.|

---

## views and Blade templates

- All Blade templates are views, but not all views are Blade templates. Blade is a powerful tool that enhances the way you create views in Laravel, allowing for cleaner, more maintainable code.
- Using Blade templates is the best practice in Laravel development as it leverages the framework's full capabilities for rendering views efficiently.

| |views | Blade templates|
|:----|:----|:----|
|File Extension |.php or .blade.php|.blade.php|
|Functionality |Basic rendering of HTML/PHP |Dynamic rendering with advanced syntax|
|Features| Limited to HTML/PHP| Supports control structures, components, and template inheritance|
|Usage| Returned via view() helper| Defines the content and structure of the view using Blade syntax|

---

## Using migrations and the Eloquent ORM in Laravel instead of over directly dealing with the database using raw SQL

- Using migrations and the Eloquent ORM in Laravel enhances your development process by providing a structured, consistent, and easier way to manage database interactions and schema changes. This leads to more maintainable and less error-prone code, especially in collaborative environments.
