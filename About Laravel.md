# About Laravel

## What is the MVC?

- MVC (Model-View-Controller) is a design pattern helps keep the application organized by separating the data (Model), user interface (View), and application logic (Controller).

|Model |View |Controller|
|:----|:----|:----|
|Handles data and business logic.|Displays data to the user and handles the presentation layer.|Manages communication between the Model and the View.|
|Interacts with the database to retrieve and manipulate data.|Contains the HTML, CSS, and JavaScript code that users interact with.|Receives input from the user (through HTTP requests), processes it using the Model, and returns the appropriate View.|
|Example in Laravel: Eloquent ORM is used to interact with database tables.|Example in Laravel: Blade templates are used for views.|Example in Laravel: Controllers are created to handle the business logic and determine which data is passed to the View.|

- Model: Represents the data and business logic.
- View: Represents the UI (User Interface).
- Controller: Handles user input and interacts with the model to update the view.

---

## Laravel request lifecycle?

- The Laravel lifecycle starts when a server receives a request and directs it to the `public/index.php` file, which acts as the entry point.
- Laravel then loads the necessary framework components via service providers.
- The request passes through middleware before reaching the router.
- The router dispatches the request to the appropriate controller or closure, which generates a response.
- The response travels back through the middleware for any post-processing, and is then sent to the user.

- The Laravel request life cycle includes the following steps:
  - Request: The user sends an HTTP request.
  - Service Container: The request is passed to the service container.
  - Routing: The router matches the request to a route.
  - Controller: If the route has an associated controller, it is called.
  - Middleware: Any middleware for the route is executed.
  - Response: A response is returned to the user.

---

## GET route vs POST route

| |GET route | POST route|
|:----|:----|:----|
|Purpose| used to retrieve data from the server. fetching information without modifying any data. |used to send data to the server.creating or updating resources, like submitting a form.|
|Characteristics| Data is passed via the URL.Less secure |Data is sent in the body of the HTTP request (not visible in the URL).More secure|
| |GET is for retrieving data.|POST is for sending or modifying data.|

---

## PUT route vs PATCH route

| |PUT route | PATCH route|
|:----|:----|:----|
|Purpose| Replace the entire resource.|Update specific fields.|
|Input Required|Complete resource data. |Only the fields to update.|

---

## Route::resource vs Route::apiResource vs Route::controller

| |Route::resource | Route::apiResource | Route::controller|
|:----|:----|:----|:----|
|Purpose|Automatically generates routes for a resourceful controller that typically handles CRUD operations.| Similar to `Route::resource`, but excludes routes like `create` and `edit` since they are not needed in API development.|Manually maps a set of routes to controller methods using a single declaration.|
|Use Case|When you need both web-based and API-compatible CRUD routes (including routes like `create` and `edit` for rendering forms).|When building RESTful APIs, where `create` and `edit` routes are unnecessary.| When you want more flexibility in naming routes and actions or the controller doesn't strictly follow CRUD operations.|

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

## What is a template engine in Laravel?

- Blade is Laravel’s templating engine. It separates the application logic from the view by allowing the use of simple directives like `@if`, `@foreach`, and `@yield`, making views easier to manage and more flexible.

---

## When should you use Single Auth and Multi Auth?

- Single Auth: When your application requires one authentication system for all users.
- Multi Auth: When your application requires different authentication systems for different user types (e.g., `admin`, `user`, and `vendor`), each with its own credentials and roles.

---

## What is CSRF (Cross-Site Request Forgery)?

- CSRF is a type of attack where a malicious user sends a request from an authenticated user's browser without their consent. Laravel protects against CSRF attacks by requiring a token for all state-changing requests (e.g., `POST`, `PUT`, `DELETE`).

---

## What is a Route?

- A Route is a way to map an HTTP request to a specific controller or action in your Laravel application. Routes define the URLs users can access and the corresponding logic to execute.

---

## What is X-Blade Component?

- X-Blade Component is a feature in Laravel that allows you to define reusable view components using Blade syntax. They encapsulate HTML and logic into a single reusable component.

---

## What is Seeder & Factory?

- Seeder: Used to populate the database with test data or default values.
- Factory: Used to create fake data for testing and seeding using model factories.

---

## What is Composer?

- Composer is a dependency management tool for PHP. It helps in managing packages and libraries that your application depends on.

---

## Service Container VS Service Provider

- `Service Container` as a dependency manager or a box where Laravel keeps all the objects, classes, and services it needs to run the application.
  - It’s like a toolbox: Whenever Laravel (or you) need a specific tool (class, service, etc.), the Service Container knows how to find or build it.
  - It handles dependency injection, which means it automatically provides the objects or values a class needs to function.
- A `Service Provider` is a configuration file (or a manager) that tells the Service Container what to store in its toolbox and how to store it.
  - It’s like a blueprint: It registers new services or objects with the Service Container.
  - Laravel already comes with many default Service Providers (e.g., for routing, database, and session), and you can create your own.

- Imagine a restaurant:
  - `Service Provider`: It’s like the `chef's recipe`. It defines how to prepare a dish.
  - `Service Container`: It’s the `kitchen`, where ingredients and tools (from the recipes) are stored and used to make the dish.

---

## Facades, Dependency Injection, and Helper Functions

- `Facades` as shortcuts to access services or classes registered in Laravel’s Service Container. They make it easy to call commonly used functionality without having to manually resolve or instantiate the class.
  - Analogy: A remote control. Instead of fiddling with the TV directly, you press a button to perform an action (like changing the channel).
  - Why Use? They’re convenient because you don’t need to worry about creating instances or managing dependencies.

- `Dependency Injection (DI)` is a way to pass the things (classes, services, etc.) that your class needs directly into it, instead of creating them inside the class. This makes your code more flexible and testable.
  - Analogy: Imagine your class is like a worker who needs tools to do their job. Instead of forcing the worker to find their own tools, you give them the tools they need.
  - Why Use? It allows you to easily swap out or change dependencies without rewriting the class.

- `Helper Functions`are simple utility functions that don’t require classes or objects. They’re quick and convenient for repetitive or small tasks. Laravel provides a lot of built-in helpers, and you can also define your own.
  - Analogy: A Swiss Army Knife. You pull out the exact tool you need for a quick task.
  - Why Use? They’re quick, easy, and don’t require much setup.

---

## What are events and listeners, and how do you use them?

- Events: Represent an occurrence that the application is listening for.
- Listeners: Classes that handle the events and perform actions in response to them (e.g., sending an email when a user registers).

---

## What are queues and jobs?

- Queue: A mechanism to defer the execution of time-consuming tasks (e.g., sending emails) to avoid slowing down the application.
- Job: A specific task that is pushed onto the queue to be processed later.

---

## What design patterns have you used in your projects?

---

## What factors affect performance or speed of a website in terms of front-end and back-end?

- Front-end: Optimizing images, minimizing CSS and JavaScript, and implementing lazy loading can improve performance.
- Back-end: Optimizing database queries, using caching, reducing redundant operations, and using queues for time-consuming tasks improve server-side performance.

---

## What is N+1 Query?

- The N+1 Query Problem occurs when a query is executed for each item in a collection (e.g., retrieving 100 users and then 100 queries for their posts), leading to unnecessary database queries and performance issues.

---

## What is Service Layer?

- The Service Layer pattern separates business logic into services. This layer contains logic that interacts with repositories and performs actions for the application, promoting cleaner and more maintainable code.

---

## What is a Collection?

- Collection is an object that wraps around an array and provides helpful methods for data manipulation. Laravel collections are based on the `Illuminate\Support\Collection` class and provide a fluent interface for working with arrays.

---

## What is Model Binding?

- Model Binding in Laravel automatically injects model instances into routes or controller methods based on route parameters.

---

## How do you optimize a specific query for performance?

- You can optimize a query by:
  - Using indexes on frequently queried columns.
  - Avoiding N+1 queries by using eager loading.
  - Using select() to retrieve only the necessary columns.
  - Caching query results.

---

## What are Config Files?

- Config Files in Laravel store configuration settings for various application aspects (e.g., database, caching, mail) and are located in the config directory.

---

## What is Throttling?

- Throttling is a technique used to limit the number of requests a user can make to an API or server in a given period to prevent abuse and ensure fair resource usage.

---

## What is the difference between Observer and Triggers?

- Observer: In Laravel, an observer listens for Eloquent model events (e.g., saving, deleted) and acts on them.
- Triggers: In databases, triggers are database-level objects that automatically execute predefined actions in response to certain events on a table, such as `INSERT`, `UPDATE`, or `DELETE`.

---

## What is Migration?

- Migration in Laravel is a version control system for database schema changes. It allows you to define database tables and their structure in PHP code.

---

## What is a Transaction?

- A Transaction in databases ensures that a set of operations is completed successfully. If any operation fails, the transaction can be rolled back to maintain data consistency.

---

## What is the difference between SQL Query, Query Builder, and ORM (Eloquent)?

- SQL Query: Raw SQL queries written manually.
- Query Builder: Laravel's fluent interface for building SQL queries without writing raw SQL.
- ORM (Eloquent): A higher-level abstraction for working with database records as PHP objects, providing an object-oriented approach.

---

## Using migrations and the Eloquent ORM in Laravel instead of over directly dealing with the database using raw SQL

- Using migrations and the Eloquent ORM in Laravel enhances your development process by providing a structured, consistent, and easier way to manage database interactions and schema changes. This leads to more maintainable and less error-prone code, especially in collaborative environments.

---

## How does the Spatie Permissions package work in the database?

The Spatie Permissions package creates tables to store roles, permissions, and their relationships. It uses `role_user` and `permission_role` pivot tables to assign roles to users and permissions to roles.

---

## What is SQL Injection?

- SQL Injection is a security vulnerability where an attacker can execute arbitrary SQL code in a web application's database by manipulating query strings or form inputs.
