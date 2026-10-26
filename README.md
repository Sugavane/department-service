
# Department Service REST API

## Project Overview
Department Service is a REST API microservice developed using Java and Spring Boot. It provides CRUD operations to create, retrieve, update, and delete department information. Department data is stored in a MySQL database using Spring Data JPA.

## Technologies Used
- Java 21
- Spring Boot 3.5.6
- Spring Web
- Spring Data JPA
- MySQL
- Maven
- Jakarta Bean Validation
- Postman

## Features
- Create a department
- Retrieve all departments
- Retrieve a department by ID
- Update department information
- Delete a department
- Validate department name and code
- Handle validation errors
- Handle department-not-found errors
- Persist department information in MySQL

## Department Fields
- `id`: Automatically generated department ID
- `departmentName`: Department name (required)
- `departmentCode`: Department code (required)
- `description`: Department description (optional)

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/departments` | Get all departments |
| GET | `/api/departments/{id}` | Get department by ID |
| POST | `/api/departments` | Create a department |
| PUT | `/api/departments/{id}` | Update a department |
| DELETE | `/api/departments/{id}` | Delete a department |

Base URL: `http://localhost:8081`

## Sample Request

### Create a Department

**POST** `/api/departments`

```json
{
  "departmentName": "Information Technology",
  "departmentCode": "IT001",
  "description": "Information Technology Department"
}
```

### Update a Department

**PUT** `/api/departments/1`

```json
{
  "departmentName": "IT Updated",
  "departmentCode": "IT001",
  "description": "Updated Information Technology Department"
}
```

## Validation
- Department name cannot be blank.
- Department code cannot be blank.
- Department name cannot exceed 100 characters.
- Department code cannot exceed 20 characters.
- Description cannot exceed 255 characters.

Invalid input returns HTTP 400 Bad Request.

## Exception Handling
- Validation errors return HTTP 400 Bad Request.
- A department that does not exist returns HTTP 404 Not Found.

## Database Configuration
The application uses MySQL with the database name `department_db`.

Configure the following properties in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/department_db
spring.datasource.username=root
spring.datasource.password=${DB_PASSWORD}
spring.jpa.hibernate.ddl-auto=update
```

Set the `DB_PASSWORD` environment variable to your local MySQL password. Do not commit database passwords or other secrets to GitHub.

## How to Run the Project
1. Install Java and MySQL.
2. Create the MySQL database named `department_db`.
3. Configure the `DB_PASSWORD` environment variable.
4. Open the project in Spring Tool Suite or Eclipse.
5. Update the Maven project dependencies.
6. Run `DepartmentServiceApplication.java` as a Spring Boot App.
7. Test the endpoints using Postman.

The application runs on port `8081`.

## Testing
The REST API endpoints have been tested using Postman for CRUD operations, and validation has been tested with invalid input.

## Author
Sugavanesh J
