# Employee-Management-Api

## Description
The Employee Management API is a backend application designed to manage employee information within a company. This system supports full CRUD (Create, Read, Update, Delete) operations for employee data and uses Spring Boot for backend development and MySQL as the database.

---

## Features
- **CRUD Operations**:
  - Add new employees.
  - Retrieve employee details (all employees or by ID).
  - Update existing employee information.
  - Delete employees.
- **Fields**:
  - ID
  - Name
  - Email
  - Role
  - Department
- **Validation**:
  - Uses `@Valid` and `@NotNull` to ensure data integrity.

---

## Tech Stack
- **Backend**: Spring Boot
- **Database**: MySQL
- **Validation**: Hibernate Validator (via Spring Boot)

---

## Learning Goals
- Develop RESTful APIs using Spring Boot.
- Perform database operations with Spring Data JPA.
- Apply data validation using `@Valid` and `@NotNull` annotations.

---

## Project Structure
```
src/
├── main/
│   ├── java/
│   │   └── com.example.employee/
│   │       ├── controller/    # REST Controllers
│   │       ├── entity/        # Entity Classes
│   │       ├── repository/    # Data Access Layer
│   │       └── EmployeeManagementApplication.java  # Main Application
│   └── resources/
│       ├── application.properties # Database Configurations
│       └── static/                 # Static Resources (Optional)
└── test/
```

---

## Endpoints
### Base URL: `/api/employees`

| HTTP Method | Endpoint           | Description                    |
|-------------|--------------------|--------------------------------|
| GET         | `/`                | Retrieve all employees         |
| GET         | `/{id}`            | Retrieve an employee by ID     |
| POST        | `/`                | Create a new employee          |
| PUT         | `/{id}`            | Update an existing employee    |
| DELETE      | `/{id}`            | Delete an employee by ID       |

---

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd employee-management
   ```

2. **Configure the Database**:
   - Open `src/main/resources/application.properties`.
   - Update the following properties with your MySQL credentials:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```

3. **Build the Project**:
   ```bash
   mvn clean install
   ```

4. **Run the Application**:
   ```bash
   mvn spring-boot:run
   ```

5. **Test the API**:
   - Use tools like Postman or cURL to test the endpoints.

---

## Database Schema
```sql
CREATE TABLE employee (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    role VARCHAR(255) NOT NULL,
    department VARCHAR(255) NOT NULL
);
```

---

## Future Enhancements
- Implement pagination and sorting.
- Add role-based authentication.
- Create a frontend interface to interact with the API.

---

## Contributing
Contributions are welcome! Feel free to fork this repository and submit pull requests for new features or bug fixes.

---

## License
This project is licensed under the [MIT License](LICENSE).

