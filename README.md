**Laravel DDD Pattern Application**

=====================================
**Overview**

The application is structured into three main layers: Application, Domain, and Infrastructure.
Application Layer
Location

## Application / Purpose

This layer contains all the application logic and acts as a bridge between the domain and the infrastructure layers. It includes controllers, services, and other mechanisms that drive the application flow.
Contents

All content originally in Laravel's app/ directory has been moved here. Mainly should contain:

Framework-Specific Services: Services specific to Laravel, such as controllers, middleware, service providers, broadcast channels....

### Domain/Purpose

Dedicated to housing all business logic and domain-specific code. This layer is framework-agnostic and focuses solely on business rules.
Contents

## Entities:

Core classes that represent business objects and their inherent logic. These are typically rich models, containing both state and behavior related to the business domain.

### Value Objects:

Immutable objects that represent descriptive aspects of the domain with no conceptual identity (e.g., Money, DateRange, Address).
Aggregates: A cluster of domain objects that can be treated as a single unit. An aggregate will have one of its component objects be the aggregate root.

### Domain Services:

Stateless services that encapsulate domain logic that doesn’t naturally fit within an entity or value object.

### Domain Events:

Events that represent something significant happening in the domain. These are used to trigger side effects across different parts of the application in a loosely coupled manner.

### Repositories Interfaces:

Abstractions for how the domain layer retrieves data from the infrastructure layer, ensuring separation of concerns.

### Factories:

Classes or methods used for creating complex domain objects.

### Specifications:

Classes that encapsulate some business logic, typically used for validation or selection criteria.

### Policies:

Classes or methods representing business rules or decisions.

Infrastructure Layer
Location

Infrastructure/
Purpose

Contains implementations of interfaces defined in the domain layer, such as repositories or external services. This layer interacts with the database and external systems.
Contents

### Repositories:

Implementations of domain interfaces for data access, typically involving Eloquent models.

### External Services Integration:

Code for integrating external APIs and services.

### Utilities and Helpers:

Utility classes and helper functions that assist in infrastructure-related tasks.

### Mail and Notification Services:

Infrastructure for sending emails and notifications.

### Queue Management:

Implementation of job queues and workers.

#### To get started with this application, follow these steps:

1. Clone the repository and install dependencies using composer install
2. Configure the database connection in the .env file.
3. Run below commands

`php artisan cache:table`

`php artisan migrate`

`php artisan migrate:refresh --seed`

`php artisan serve`

4. After that open Postman and make below Curl Request

`curl --location --request POST 'localhost:8000/api/project/1/users' `
