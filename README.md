# Employee Management System

A comprehensive Spring Boot application for managing employees, leave requests, duties, and administrative functions.

## Features

- **Employee Management**: Add, update, and manage employee information
- **Leave Management**: Request and approve leave with tracking
- **Duty Assignment**: Assign duties to employees with management capabilities
- **User Authentication**: Secure JWT-based authentication and authorization
- **Admin Panel**: Administrative controls for user and system management
- **Manager Dashboard**: Tools for managers to oversee their team
- **Email Notifications**: Automated email notifications for various events
- **Password Reset**: Secure password reset functionality with token validation
- **REST API**: Complete REST API with Swagger/OpenAPI documentation

## Tech Stack

- **Framework**: Spring Boot
- **Language**: Java
- **Database**: (Configured in application.properties)
- **Authentication**: JWT (JSON Web Tokens)
- **API Documentation**: Swagger/OpenAPI
- **Build Tool**: Maven

## Project Structure

```
src/
├── main/
│   ├── java/com/klef/fsad/sdp/
│   │   ├── EmployeeManagementSystemApplication.java
│   │   ├── config/                 # Configuration classes
│   │   │   └── OpenAPIConfig.java
│   │   ├── controller/             # REST Controllers
│   │   │   ├── AdminController.java
│   │   │   ├── AuthController.java
│   │   │   ├── EmployeeController.java
│   │   │   └── ManagerController.java
│   │   ├── dto/                    # Data Transfer Objects
│   │   │   └── LoginRequest.java
│   │   ├── model/                  # Entity Models
│   │   │   ├── Admin.java
│   │   │   ├── Employee.java
│   │   │   ├── Manager.java
│   │   │   ├── Leave.java
│   │   │   ├── Duty.java
│   │   │   ├── Email.java
│   │   │   ├── ForgotPassword.java
│   │   │   └── ResetToken.java
│   │   ├── repository/             # Data Access Layer
│   │   │   ├── AdminRepository.java
│   │   │   ├── EmployeeRepository.java
│   │   │   ├── ManagerRepository.java
│   │   │   ├── LeaveRepository.java
│   │   │   ├── DutyRepository.java
│   │   │   ├── EmailRepository.java
│   │   │   └── ResetTokenRepository.java
│   │   ├── security/               # Security Components
│   │   │   └── JWTUtilizer.java
│   │   └── services/               # Business Logic
│   │       ├── AdminService.java
│   │       ├── AdminServiceImpl.java
│   │       ├── EmployeeService.java
│   │       ├── EmployeeServiceImpl.java
│   │       ├── ManagerService.java
│   │       ├── ManagerServiceImpl.java
│   │       ├── LeaveService.java
│   │       ├── LeaveServiceImpl.java
│   │       ├── DutyService.java
│   │       ├── DutyServiceImpl.java
│   │       └── EmailService.java
│   └── resources/
│       ├── application.properties   # Application configuration
│       └── static/
│           └── index.html
└── test/                           # Unit Tests
```

## Prerequisites

- Java 8 or higher
- Maven 3.6+
- Database (MySQL, PostgreSQL, etc.)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/saichandramsce/ReferIT.git
   cd SpringBootEMS-EmployeeManagementSystem
   ```

2. **Configure Database**
   - Edit `src/main/resources/application.properties`
   - Set your database connection details:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/ems_db
     spring.datasource.username=your_db_user
     spring.datasource.password=your_db_password
     spring.jpa.hibernate.ddl-auto=update
     ```

3. **Build the application**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn spring-boot:run
   ```
   
   Or using the Maven wrapper:
   ```bash
   ./mvnw spring-boot:run
   ```

The application will start on `http://localhost:8080`

## API Documentation

Once the application is running, access the Swagger UI at:
```
http://localhost:8080/swagger-ui.html
```

## Core Endpoints

### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration

### Employee
- `GET /employee` - Get all employees
- `GET /employee/{id}` - Get employee by ID
- `POST /employee` - Create new employee
- `PUT /employee/{id}` - Update employee
- `DELETE /employee/{id}` - Delete employee

### Leave Management
- `GET /leave` - Get all leaves
- `POST /leave/request` - Request leave
- `PUT /leave/{id}/approve` - Approve leave request
- `PUT /leave/{id}/reject` - Reject leave request

### Duty Management
- `GET /duty` - Get all duties
- `POST /duty` - Create new duty
- `PUT /duty/{id}` - Update duty
- `DELETE /duty/{id}` - Delete duty

### Admin
- `GET /admin/users` - Get all users
- `POST /admin/reset-password` - Reset user password

## Configuration

Edit `application.properties` to configure:
- Server port
- Database connection
- JWT secret and expiration
- Email settings
- Logging levels

## Authentication

The application uses JWT tokens for authentication. Include the token in the `Authorization` header:
```
Authorization: Bearer <your_jwt_token>
```

## Features Details

### Leave Management
- Employees can request leave
- Managers and admins can approve/reject requests
- Automatic email notifications
- Leave balance tracking

### Duty Assignment
- Create and assign duties to employees
- Track duty completion status
- Manage duty schedules

### Password Reset
- Secure token-based password reset
- Email verification
- Token expiration handling

## Testing

Run unit tests using:
```bash
mvn test
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Support

For support, please contact the development team or open an issue on GitHub.

## Author

Created by Saichandra - [GitHub](https://github.com/saichandramsce)

---

**Last Updated**: January 28, 2026
