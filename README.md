# Airbnb Clone Backend

## About

Full-stack booking platform simulating Airbnb's core functionality. Focus on scalable backend architecture, secure APIs, and modern development workflows.

---

## Objectives

- Master GitHub collaborative workflows  
- Implement robust backend architecture and database design  
- Build secure API endpoints with advanced authentication  
- Design and manage CI/CD pipelines  
- Integrate Django, MySQL, and GraphQL ecosystem  

---

## Tech Stack

- **Django** – Backend framework  
- **MySQL** – Database  
- **GraphQL** – API layer  
- **GitHub Actions** – CI/CD  
- **JWT** – Authentication  
- **Docker** – Containerization  

---

## Core Features

- User authentication and authorization  
- Property listings and search  
- Booking management system  
- Payment processing integration  
- Review and rating system  
- Real-time messaging  

---

## Team Roles

- **Backend Developer**: Designs and implements server-side logic, APIs, and database interactions using Django.  
- **Database Administrator**: Manages database design, optimization, and security; ensures data integrity across all entities.  
- **DevOps Engineer**: Sets up CI/CD pipelines, manages infrastructure, and ensures smooth integration between development and operations.  
- **QA Engineer**: Develops testing strategies, performs manual and automated testing to ensure application quality and reliability.  

---

## Technology Stack

| Component         | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Django**        | Web framework for building RESTful APIs and handling server-side logic     |
| **PostgreSQL**    | Relational DB for user data, properties, bookings, and transactions        |
| **GraphQL**       | API layer for flexible data querying and efficient client-server interaction |
| **GitHub Actions**| CI/CD for automated testing, building, and deployment                      |
| **Docker**        | Containerization for consistent dev and prod environments                  |
| **JWT**           | Token-based authentication for secure sessions                             |

---

## Database Design

### Core Entities

#### BaseModel
- `id` (Primary Key)  
- `created_at` (Timestamp)  
- `updated_at` (Timestamp)  

#### Users
- Fields: `name`, `email`, `password`, `phone`, `is_host`  
- Relationships: One-to-many with Properties and Bookings  

#### Properties
- Fields: `name`, `address`, `price_per_night`, `owner_id`, `amenities`  
- Relationships: Belongs to User (owner), has many Reviews and Bookings  

#### Bookings
- Fields: `user_id`, `property_id`, `start_date`, `end_date`, `total_price`  
- Relationships: Belongs to User and Property, one-to-one with Payment  

#### Reviews
- Fields: `user_id`, `property_id`, `rating`, `comment`  
- Relationships: Belongs to User and Property  

#### Payments
- Fields: `user_id`, `booking_id`, `amount`, `status`, `payment_method`  
- Relationships: Belongs to User and Booking  

> All entities inherit common attributes from BaseModel for consistent data tracking.

---

## Feature Breakdown

### User Management
- Registration, login, profile management  
- Role-based access control (guests vs hosts)  

### Property Management
- Hosts can list, update, and manage properties  
- Support for photos, amenities, pricing, availability calendars  

### Booking System
- Reservation flow with availability checks and cancellation handling  
- Business logic validation  

### Review System
- Guests review properties  
- Hosts review guests  
- Reputation management for platform trust  

### Payment Processing
- Secure payments and refunds  
- Payouts to hosts  
- Financial tracking and audit  

---

## API Security

- **JWT Authentication**: Secure user sessions and route protection  
- **Role-Based Authorization**: Access control based on user roles  
- **Input Validation**: Prevent SQL injection and bad data  
- **Data Encryption**: Passwords, payments, and sensitive user info  
- **Rate Limiting**: Prevent DDoS and abuse  
- **PCI DSS Compliance**: Secure financial transactions  

---

## CI/CD Pipeline

### Goals
Automate the software delivery process, ensure code quality, and enable reliable deployments.

### Tools & Workflow

- **GitHub Actions**:  
  - Run tests  
  - Code quality checks  
  - Trigger deployments on push  
- **Docker**:  
  - Containerized app setup for dev, staging, and production  
- **Automated Testing**:  
  - Unit tests  
  - Integration tests  
  - Security scans  

**Benefits**:  
- Faster development cycles  
- Fewer manual errors  
- Consistent, reliable deployments  

