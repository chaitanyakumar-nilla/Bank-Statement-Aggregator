# Bank Statement Aggregator

## Overview

The **Bank Statement Aggregator** is a Spring Boot-based application designed to collect, process, and aggregate bank statements from multiple branches across various banks. It facilitates user authentication, bank statement generation in predefined formats, file uploads to AWS S3, and processing of these statements into structured Java objects for storage in a relational database.

---

## Features

- **User Authentication**: Secure user authentication and role management.
- **Multi-Bank and Multi-Branch Support**: Aggregate bank statements from different branches and banks.
- **File Handling**: Upload and download bank statements in predefined formats such as CSV.
- **AWS S3 Integration**: Store and retrieve bank statements from AWS S3.
- **Data Processing**: Convert uploaded bank statements into Java objects and store them in the database.
- **Database Management**: Relational database schema for handling companies, users, branches, bank statements, and transactions.

---

## Technology Stack

- **Backend**: Java, Spring Boot, Hibernate
- **Database**: MySQL
- **File Storage**: AWS S3
- **Authentication**: Spring Security
- **Frontend**: HTML, CSS, JavaScript
- **Build Tool**: Maven

---

## Installation and Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/bank-statement-aggregator.git
   cd bank-statement-aggregator
   
2. **Configure Database**
   - Update the application.properties file with your MySQL database credentials.
    spring.datasource.url=jdbc:mysql://localhost:3306/yourdbname
    spring.datasource.username=yourusername
    spring.datasource.password=yourpassword

3. **AWS S3 Configuration**
   - Add your AWS S3 credentials and bucket details in the application.properties.
     aws.access-key=your-access-key
     aws.secret-key=your-secret-key
     aws.bucket-name=your-bucket-name
     
4. **Run the Application**
    - Use Maven to build and run the application.
      mvn spring-boot:run
5. **Access the Application**
    The application will be running at http://localhost:8080.

**Database Schema**
The application uses a relational database with the following schema:

**Companies:** Information about the companies.
**Users:** Authentication and role-based access control.
**Branches:** Details of the bank branches.
**Bank Statements:** Uploaded bank statements in CSV format.
**Transactions:** Processed transactions from the bank statements.

**API Endpoints**
Here are some example API endpoints:

**Authentication:**
POST /login: User login.
POST /register: New user registration.

**Bank Statements:**
GET /statements: Fetch bank statements.
POST /statements/upload: Upload a new bank statement.
GET /statements/{id}: Get details of a specific statement.

**Challenges**
Integrating AWS S3 for secure file storage.
Ensuring efficient processing and handling of large CSV files.
Designing a flexible schema for multi-bank and multi-branch operations.

**Future Enhancements**
PDF Support: Enable PDF format support for statement uploads.
Improved Analytics: Provide a dashboard with analytics and reporting features.
Third-Party Integrations: Integrate with other financial APIs for real-time data fetching.
