# spring-boot-jwt-auth-demo
Spring Boot JWT Authentication and Authorization using Spring Security, JWT, H2 Database, and JDBC UserDetailsManager.


# Spring Boot JWT Authentication Demo

A Spring Boot application that demonstrates secure authentication and authorization using JSON Web Tokens (JWT) and Spring Security.

## 🚀 Features

- JWT Authentication
- Spring Security Integration
- Stateless Session Management
- Role-Based Authorization
- H2 In-Memory Database
- JDBC UserDetailsManager
- BCrypt Password Encryption
- Custom JWT Authentication Filter
- Custom Unauthorized Access Handling

---

## 🛠️ Tech Stack

- Java
- Spring Boot
- Spring Security
- JWT (JJWT)
- H2 Database
- Maven

---

## 📂 Project Structure

```text
src/main/java/com/example/securitydemo
│
├── jwt
│   ├── AuthEntryPointJwt.java
│   ├── AuthTokenFilter.java
│   ├── JwtUtils.java
│   ├── LoginRequest.java
│   └── LoginResponse.java
│
├── SecurityConfig.java
└── SecuritydemoApplication.java
```

---

## 🔐 Authentication Flow

1. User submits username and password.
2. Spring Security authenticates the user.
3. JWT token is generated.
4. JWT token is returned in the response.
5. Client sends JWT token in the Authorization header.
6. JWT Filter validates the token.
7. Protected endpoints become accessible.

---

## 👤 Default Users

| Username | Password | Role |
|----------|----------|------|
| user1 | password1 | USER |
| admin | adminPass | ADMIN |

---

## 📡 API Endpoints

### Login

```http
POST /signin
```

Request Body

```json
{
  "username": "user1",
  "password": "password1"
}
```

Response

```json
{
  "username": "user1",
  "roles": [
    "ROLE_USER"
  ],
  "jwtToken": "eyJhbGciOiJIUzI1NiJ9..."
}
```

---

### Access Protected Endpoint

```http
GET /greeting
Authorization: Bearer <jwt-token>
```

---

## ⚙️ Configuration

```properties
spring.datasource.url=jdbc:h2:mem:test

spring.app.jwtExpirationMs=3000000
spring.app.jwtSecret=YOUR_SECRET_KEY
```

---

## ▶️ Run the Application

### Clone Repository

```bash
git clone https://github.com/yourusername/spring-boot-jwt-auth-demo.git
```

### Navigate to Project

```bash
cd spring-boot-jwt-auth-demo
```

### Run Application

```bash
mvn spring-boot:run
```

Application will start on:

```text
http://localhost:8080
```

---

## 🏗️ Security Components

### JwtUtils

Responsible for:

- JWT Token Generation
- JWT Token Validation
- Username Extraction

### AuthTokenFilter

- Intercepts incoming requests
- Validates JWT token
- Sets authentication in Security Context

### AuthEntryPointJwt

- Handles unauthorized requests
- Returns JSON error response

### SecurityConfig

Configures:

- Security Filter Chain
- Authentication Manager
- Password Encoder
- JWT Filter
- Stateless Session Management

---

## 📚 What I Learned

- Spring Security Fundamentals
- JWT Authentication & Authorization
- Stateless Security Architecture
- Authentication Filters
- BCrypt Password Encryption
- Database-backed User Authentication
- Secure REST API Development

---

## 🔮 Future Enhancements

- User Registration API
- Refresh Tokens
- MySQL/PostgreSQL Integration
- Swagger/OpenAPI Documentation
- Docker Support
- Role-Based Access Control (RBAC)

---

## 📜 License

This project is created for learning and educational purposes.

---

## 👨‍💻 Author

Developed as a practice project to learn Spring Security and JWT Authentication using Spring Boot.
