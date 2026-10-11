# Library Management System

## Overview
A full‑stack Library Management System built with:
- **Backend**: Java 21, Spring Boot, Spring Security, Spring Data JPA, MySQL 8
- **Frontend**: React, Vite, Tailwind CSS, React Router, Axios
- **Authentication**: Session‑based HTTP cookies
- **Features**: User registration & login, dashboard statistics, CRUD for books & members, issue/return workflow.

## Prerequisites
- **Java 21** (or later) with Maven wrapper (`mvnw`).
- **Node.js 18+** and npm.
- **MySQL 8** server running locally.
- Git (optional, for cloning).

## Database Setup
1. Start MySQL and create the database:
```sql
CREATE DATABASE library_management;
``` 
2. Update the connection details in `backend/src/main/resources/application.properties` if needed (default:
```
spring.datasource.url=jdbc:mysql://localhost:3306/library_management
spring.datasource.username=root
spring.datasource.password=your_password
```)
3. The application uses JPA `hibernate.hbm2ddl.auto=update` to create tables automatically on first run.

## Backend (Spring Boot)
1. Open a terminal in the **backend** directory:
```
cd backend
``` 
2. Build the project (skip tests for speed):
```
./mvnw.cmd package -DskipTests
``` 
3. Run the server:
```
java -jar target/librarymanagement-0.0.1-SNAPSHOT.jar
``` 
   The API will be available at `http://localhost:8081`.
   - Swagger UI: `http://localhost:8081/swagger-ui.html` (if Swagger dependency is present).

## Frontend (React + Vite)
1. Open a new terminal in the **frontend** directory:
```
cd frontend
``` 
2. Install dependencies:
```
npm install
``` 
3. Start the development server:
```
npm run dev
``` 
   The app runs at `http://localhost:5173`. It communicates with the backend on port 8081 using `axios` with `withCredentials:true`.

## Production Build (Optional)
```
npm run build
``` 
   The static files are generated in `frontend/dist`. You can serve them with any static file server or configure Spring Boot to serve them.

## Usage
- **Register** a new user at `/register`. Password and confirm password must match.
- **Login** at `/login`.
- After login you are redirected to the **Dashboard**, which shows counts of books, members, and issued books.
- Use the navigation menu to manage **Books**, **Members**, and **Issue/Return** operations.

## License
MIT
