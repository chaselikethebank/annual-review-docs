# Future Feature Set

This is a good place to take note of potential features post MVP. 

## Multitenancy with Middleware and Sanctum

Multitenancy refers to a software architecture where a single application instance serves multiple tenants, such as organizations, users, or groups. Each tenant's data is logically separated to ensure isolation and security.

## Approaches to Multitenancy in Laravel

1. **Database Per Tenant**: Each tenant has its own database.
2. **Shared Database with Tenant ID**: A single database where tenant data is distinguished by a tenant ID.
3. **Hybrid**: A combination of both approaches.

---

### Middleware

Middleware acts as a bridge between a request and the application. It inspects and modifies HTTP requests before reaching the application or HTTP responses before being sent to the client.

## Common Middleware Use Cases in Multitenancy

1. **Tenant Identification**: Detect the tenant using subdomains, request headers, or URLs.
2. **Authentication**: Enforce tenant-specific user authentication.
3. **Database Switching**: Dynamically connect to the tenant's database.

---

## Example: Middleware for Multitenancy

```php 
namespace App\Http\Middleware;

use Closure;
use Illuminate\Http\Request;

class IdentifyTenant
{
    public function handle(Request $request, Closure $next)
    {
        $tenant = $request->getHost(); // Extract tenant info from subdomain
        // Perform logic to identify the tenant (e.g., load configuration, database connection)
        // Set the tenant in a global context (e.g., a service provider or database manager)
        
        return $next($request);
    }
}


```

## Sanctum in Laravel

Sanctum is a lightweight authentication package that provides:

1. **API Token Authentication**: Issue personal access tokens for users.
2. **Session-Based Authentication**: Simplifies SPA authentication.
3. **Token Abilities**: Scope tokens with specific permissions.

---

## Sanctum in a Multitenancy Context

Sanctum can help manage tenant-specific authentication by:

1. **Scoping Tokens to Tenant IDs**: Ensure tokens are tied to specific tenants.
2. **Isolating API Authentication**: Ensure authentication is separated for each tenant.

## Setting Up Sanctum for Multitenancy
1. **Install Sanctum:**

```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```

2. **Configure Sanctum Middleware: Update the api middleware group in**
```php
'api' => [
    \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
    'throttle:api',
    \Illuminate\Routing\Middleware\SubstituteBindings::class,
],
```

3. **Issue Tokens with Tenant Context: Ensure each token is scoped to a tenant.**
```php
$token = $user->createToken('access-token', ['tenant:'.$tenant->id]);
```

4. **Guard API Routes with Middleware: Use middleware to verify tenant tokens.**

```php
Route::middleware(['auth:sanctum', 'tenant'])->group(function () {
    Route::get('/user', function (Request $request) {
        return $request->user();
    });
});

```

#### Token Abilities Example

Add specific abilities (e.g., read, write) when issuing tokens:
```php
$token = $user->createToken('access-token', ['read', 'write']);

```

```php
if ($request->user()->tokenCan('read')) {
    // Allow access
}

```

4. **Putting It All Together**

- Middleware for Tenant Identification: Identify and set the tenant based on subdomains or headers.

- Sanctum for API Authentication: Issue and validate tokens scoped to the tenant.

- Custom Database Connections: Use the tenant ID to switch database connections dynamically.

#### Example Application Flow

- A user makes a request to tenant1.example.com/api/data.
- The middleware identifies tenant1 and sets the tenant in the application context.
- Sanctum validates the API token for the tenant1 scope.
- The database connection is dynamically switched to tenant1's database.

This architecture ensures that tenant isolation is maintained at every level of the request lifecycle.






