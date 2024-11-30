# API

## What is an API, and how does Laravel support API development?

- An API (Application Programming Interface) is a set of rules and protocols that allows different software applications to communicate with each other. Laravel supports API development by providing `api.php` for API-specific routes, middleware, resource controllers, and JSON response handling.

## What are API routes, and how do they differ from web routes in Laravel?

- HTTP Method: Determines the type of action to perform:
  - `GET`: Retrieve data.
  - `POST`: Create new data.
  - `PUT/PATCH`: Update existing data.
  - `DELETE`: Remove data.
- Endpoint/URL: The path that identifies a specific resource or action in the system.
  - Example: `/api/users`, `/api/orders/123`.
- Route Handler: The function or controller that processes the request and sends the appropriate response.

- API routes are defined in `api.php` and are stateless, meaning they don’t use sessions or cookies by default. Web routes `web.php` use stateful authentication, sessions, and cookies.

## How do you create a RESTful API in Laravel?

- Steps:
  - Define routes in api.php (e.g., `Route::apiResource('posts', PostController::class);`).
  - Create a resource controller using `php artisan make:controller PostController --resource`.
  - Implement CRUD methods in the controller.
  - Test the API using tools like Postman.

## What is a resource controller in Laravel? How is it used in APIs?

- A resource controller provides predefined CRUD methods (`index`, `show`, `store`, `update`, `destroy`). It simplifies API development by adhering to RESTful standards.

## How do you handle API authentication in Laravel?

- Laravel offers:
  - Sanctum: For simple token-based authentication.
  - Passport: For OAuth2 authentication.
  - You can secure API routes using middleware like `auth:sanctum`.

## What is JSON, and why is it commonly used in APIs?

- JSON (JavaScript Object Notation) is a lightweight format for data exchange. It is human-readable and easy for machines to parse, making it ideal for APIs.

## How can you send JSON responses in Laravel?

```php
return response()->json(['message' => 'Success']);
```

- Or by directly returning arrays from controllers, which Laravel converts to JSON automatically.
