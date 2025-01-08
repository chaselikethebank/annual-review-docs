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

## # Sanctum in Laravel

Sanctum is a lightweight authentication package that provides:

1. **API Token Authentication**: Issue personal access tokens for users.
2. **Session-Based Authentication**: Simplifies SPA authentication.
3. **Token Abilities**: Scope tokens with specific permissions.

---

## Sanctum in a Multitenancy Context

Sanctum can help manage tenant-specific authentication by:

1. **Scoping Tokens to Tenant IDs**: Ensure tokens are tied to specific tenants.
2. **Isolating API Authentication**: Ensure authentication is separated for each tenant.