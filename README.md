# PROG2200_Assignment3_BryceFulton
This project is a RESTful API for a Courier Service Management System, implemented using Spring Boot and MySQL. The application allows users to manage products, payments, deliveries, and reviews through well-defined REST API endpoints.

Features
Product Management: Add, update, delete, and fetch products.
Payment Processing: Record and manage payment transactions.
Delivery Management: Schedule and track deliveries.
Review System: Add and retrieve customer reviews.
Built with Spring Boot for efficient backend operations.
Tech Stack
Backend Framework: Spring Boot
Database: MySQL
ORM: JPA (Java Persistence API)
Build Tool: Maven
Testing: Postman or cURL
Database Schema
Here is the schema for the database tables used:

Product Table:

sql
Copy code
CREATE TABLE Product (
    id BIGINT IDENTITY(1,1) PRIMARY KEY,
    name NVARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL
);
Payment Table:

sql
Copy code
CREATE TABLE Payment (
    id BIGINT IDENTITY(1,1) PRIMARY KEY,
    amount DECIMAL(10, 2) NOT NULL,
    status BIT NOT NULL
);
Delivery Table:

sql
Copy code
CREATE TABLE Delivery (
    id BIGINT IDENTITY(1,1) PRIMARY KEY,
    address NVARCHAR(255) NOT NULL,
    status NVARCHAR(50) NOT NULL
);
Review Table:

sql
Copy code
CREATE TABLE Review (
    id BIGINT IDENTITY(1,1) PRIMARY KEY,
    customer_name NVARCHAR(255) NOT NULL,
    comments NVARCHAR(MAX) NOT NULL
);
Endpoints
Product Endpoints
GET /api/products - Get all products.
POST /api/products - Add a new product.
GET /api/products/{id} - Get a product by ID.
PUT /api/products/{id} - Update a product by ID.
DELETE /api/products/{id} - Delete a product by ID.
Payment Endpoints
GET /api/payments - Get all payments.
POST /api/payments - Record a payment.
Delivery Endpoints
GET /api/deliveries - Get all deliveries.
POST /api/deliveries - Schedule a delivery.
Review Endpoints
GET /api/reviews - Get all reviews.
POST /api/reviews - Add a new review.
Setup Instructions
Prerequisites
Java 17 or higher
MySQL Server
Maven
IDE (e.g., IntelliJ IDEA, Eclipse)
Steps
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/courier-service.git
cd courier-service
Configure the Database:

Update the application.properties file with your MySQL credentials:
properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/courierservice
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.jpa.hibernate.ddl-auto=update
Create the Database:

Run the following SQL:
sql
Copy code
CREATE DATABASE courierservice;
Build and Run:

bash
Copy code
mvn clean install
mvn spring-boot:run
Test the API:

Use Postman or cURL to test endpoints.
Example POST request to add a product:
json
Copy code
POST /api/products
{
    "name": "Laptop",
    "price": 1500.00
}
