Survivor API
The Survivor API is a web-based application built using ASP.NET Core that allows for managing competitors and categories in the Survivor game. The API supports basic CRUD operations for both competitors and categories. Each competitor belongs to a single category, while a category can have multiple competitors (one-to-many relationship).

Features
Competitors CRUD operations (Create, Read, Update, Delete).
Categories CRUD operations (Create, Read, Update, Delete).
One-to-many relationship between Categories and Competitors.
RESTful API implementation.
Built using Entity Framework Core and SQL Server/InMemory Database.
Swagger integration for easy API testing.
Project Structure
The project consists of the following main components:

Entities: Represents the data models for Competitor and Category.
DbContext: SurvivorDbContext manages the database and relationships between entities.
Controllers:
CompetitorController handles competitor-related API requests.
CategoryController handles category-related API requests.
Prerequisites
To run this project locally, you need to have:

.NET 6.0 SDK
SQL Server (if not using InMemory database)
Setup Instructions
Clone the repository:

bash git clone https://github.com/your-username/survivor-api.git cd survivor-api

Install the required dependencies:

bash dotnet restore

Configure the database connection string in appsettings.json (if using SQL Server):

json { "ConnectionStrings": { "DefaultConnection": "Server=localhost;Database=SurvivorDb;Trusted_Connection=True;" } }

Add database migrations (if using SQL Server):

bash dotnet ef migrations add InitialCreate dotnet ef database update

Run the application:

bash dotnet run

Open your browser and go to:

bash https://localhost:5001/swagger

Here you can interact with the API using the Swagger interface.

API Endpoints
Competitors
GET /api/competitors: Get a list of all competitors.
GET /api/competitors/{id}: Get a specific competitor by ID.
GET /api/competitors/categories/{CategoryId}: Get competitors by category ID.
POST /api/competitors: Create a new competitor.
PUT /api/competitors/{id}: Update an existing competitor.
DELETE /api/competitors/{id}: Delete a competitor.
Categories
GET /api/categories: Get a list of all categories.
GET /api/categories/{id}: Get a specific category by ID.
POST /api/categories: Create a new category.
PUT /api/categories/{id}: Update an existing category.
DELETE /api/categories/{id}: Delete a category.
Testing the API
You can test the API using:

Swagger: Available at https://localhost:5001/swagger
Postman: Import the API endpoints and test various CRUD operations.
Database Migrations
To add new migrations when updating your models:

Create a new migration:

bash dotnet ef migrations add MigrationName

Apply the migration to the database:

bash dotnet ef database update

Technologies Used
ASP.NET Core: Backend framework for building RESTful APIs.
Entity Framework Core: ORM for interacting with the database.
SQL Server: (or InMemory for development) Database for storing the data.
Swagger: Integrated for API documentation and testing.
Dependency Injection: Used to manage service lifetimes and scope.
