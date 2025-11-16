# Todo API

A REST-based Todo Management API built with ASP.NET Core and EF Core. This application demonstrates how to implement CRUD operations for managing tasks (todos) while following clean architecture and best practices.

## Features

- Create, Read, Update, Delete (CRUD) operations for todos.
- Mark tasks as complete or incomplete.
- Follows layered architecture principles:
  - Controllers for routing and request handling
  - Services for business logic
  - Repository for database access
- Implements RESTful API principles.
- Uses Entity Framework Core for ORM (Object Relational Mapping).
- Swagger/OpenAPI integration for API documentation.
- SQL Server as the relational database.

## Endpoints

| HTTP Method | Endpoint              | Description                         |
|-------------|-----------------------|-------------------------------------|
| POST        | /api/todos            | Create a new todo                  |
| GET         | /api/todos            | Get all todos                      |
| GET         | /api/todos/{id}       | Get a specific todo by ID          |
| PUT         | /api/todos/{id}       | Update details of a todo           |
| DELETE      | /api/todos/{id}       | Delete a todo                      |
| PUT         | /api/todos/{id}/status| Mark a todo as complete/incomplete |

## Technology Stack

- **Backend Framework**: ASP.NET Core (.NET 6)
- **Database**: SQL Server
- **ORM**: Entity Framework Core
- **API Documentation**: Swagger/OpenAPI
- **Hosting**: IIS / Azure App Service

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/zunch/todo-api.git
cd todo-api
```

2. Open the project in Visual Studio or Visual Studio Code.

3. Update the `appsettings.json` file with your database connection details.

4. Apply migrations to update the database:
```bash
dotnet ef database update
```

5. Run the application:
```bash
dotnet run
```

6. Go to `http://localhost:{port}/swagger` to test the API endpoints.

## Example Database Schema

```sql
CREATE TABLE Todos (
    Id INT PRIMARY KEY IDENTITY,
    Title NVARCHAR(255) NOT NULL,
    Description NVARCHAR(MAX),
    IsCompleted BIT NOT NULL DEFAULT 0,
    CreatedDate DATETIME NOT NULL DEFAULT GETDATE()
);
```

## Future Enhancements

- Add support for authentication and authorization using JWT.
- Implement paging, sorting, and filtering capabilities for APIs.
- Unit tests for service and controller layers.
- Support for additional database providers (e.g., PostgreSQL, MySQL).