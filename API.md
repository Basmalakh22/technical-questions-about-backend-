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

- Define routes in api.php (e.g., `Route::apiResource('posts', PostController::class);`).
- Create a resource controller using `php artisan make:controller PostController --resource`.
- Implement CRUD methods in the controller.
- Test the API using tools like Postman.

## What is a resource controller in Laravel? How is it used in APIs?

- A resource controller provides predefined CRUD methods (`index`, `show`, `store`, `update`, `destroy`). It simplifies API development by adhering to RESTful standards.

## What is the difference between apiResource and resource routes in Laravel?

- `apiResource`: Generates routes for API-friendly CRUD operations (`index`, `show`, `store`, `update`, `destroy`). Excludes routes like create and edit, as these are for HTML forms in web apps.
- `resource`: Includes all CRUD routes, including `create` and `edit`.

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

```php
return ['message' => 'Success'];
```

## What is the difference between an API and a Web Service?

- API: Broader concept, allowing communication between any two software components.
- Web Service: A subset of APIs, specifically those that operate over the web using standard protocols like HTTP.
- All web services are APIs, but not all APIs are web services.

## What is the purpose of status codes in API responses?

- HTTP status codes indicate the result of an API request:
  - `200 OK`: Request succeeded.
  - `201 Created`: Resource created successfully.
  - `400 Bad Request`: The server couldn't understand the request due to invalid input.
  - `401 Unauthorized`: Authentication is required.
  - `404 Not Found`: The requested resource is unavailable.
  - `500 Internal Server Error`: Server-side issue.

## What is the difference between PUT and PATCH?

- `PUT`: Replaces the entire resource.
  - Example: Update a user’s profile with a new set of data.
- `PATCH`: Partially updates a resource.
  - Example: Only updating a user’s email address.

## How do you secure an API?

- Authentication: Verify the user's identity (e.g., API keys, OAuth tokens).
- Authorization: Ensure the user has the right permissions.
- Encrypt Communication: Use HTTPS to secure data.
- Rate Limiting: Limit the number of requests to prevent abuse.
- CORS: Control which domains can access your API.

## How do you handle versioning in Laravel APIs?

- Use version prefixes in routes (`Route::prefix('v1')->group(...)`) or subdomains (`v1.api.example.com`). Include the version in headers (`Accept: application/vnd.api.v1+json`).

## What is rate limiting, and how do you implement it in Laravel APIs?

Rate limiting restricts the number of requests from a client. Configure it in RouteServiceProvider using the RateLimiter class:

```php
RateLimiter::for('api', function () {
    return Limit::perMinute(60);
});
```

## How do you validate API requests in Laravel?

- Use `FormRequest` classes:

```php
public function rules() {
    return ['title' => 'required|string|max:255'];
}
```

- Or inline validation

```php
$request->validate(['title' => 'required']);
```

## What is API middleware, and how is it used?

- Middleware processes requests before they reach the controller.
  - Example: `auth:sanctum` for authentication, or custom middleware for logging or CORS.

## How do you implement pagination in API responses?

```php
$posts = Post::paginate(10);
return response()->json($posts);
```

- Laravel automatically includes metadata like `current_page` and `last_page`.

## What are API resources in Laravel? How do they help?

- API resources (JsonResource) transform models into structured JSON responses:

```php
return new PostResource($post);
```

## How do you secure APIs in Laravel?

- Use HTTPS, middleware for authentication (`auth:sanctum`), validation for inputs, and rate limiting.

## What is the difference between Laravel Sanctum and Passport? When would you use each?

- Sanctum: Simple, lightweight token management for SPAs and mobile apps.
- Passport: Comprehensive OAuth2 implementation for complex scenarios requiring scopes and third-party integrations.

## How do you handle API errors in Laravel?

- Use `App\Exceptions\Handler` for centralized error handling. Return custom error responses:

```php
return response()->json(['error' => 'Not Found'], 404);
```

## How do you implement file uploads in Laravel APIs?

```php
$file = $request->file('photo')->store('photos');
return response()->json(['path' => $file]);
```

## What is CORS, and how do you configure it in Laravel?

CORS (Cross-Origin Resource Sharing)  is a security feature that restricts how resources on a server can be accessed by external domains. Configure it in `config/cors.php` and add the `\Fruitcake\Cors\HandleCors` middleware.

## What is a webhook, and how would you handle it in Laravel?

A webhook is a URL that receives POST requests from external systems. Example

```php
Route::post('/webhook', function (Request $request) {
    // Process payload
    return response('OK');
});
```

## How do you test Laravel APIs?

- Use feature tests

```php
$this->postJson('/api/posts', ['title' => 'Test'])
     ->assertStatus(201);
```

- Or test manually using Postman.

## How do you optimize API performance in Laravel?

- Use caching (Redis, query caching), optimize database queries (eager loading), and compress JSON responses.

