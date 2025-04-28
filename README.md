# Airbnb Clone Project

## 📄 Project Overview
This project is a backend clone of Airbnb, designed to manage user registrations, property listings, bookings, payments, and reviews. It aims to mimic the core features of the Airbnb platform with a focus on building scalable and maintainable backend services.

## 🎯 Project Goals
- User management (registration, authentication, profiles)
- Property listing management (create, update, delete properties)
- Booking system for users to reserve properties
- Payment processing for booking transactions
- Review system for users to review properties
- Optimize database performance with indexing and caching

## 🛠️ Tech Stack
- **Backend Framework:** Django
- **API Framework:** Django REST Framework (DRF)
- **Database:** PostgreSQL
- **Query Language:** GraphQL (optional for flexible queries)
- **Task Queue:** Celery
- **Cache:** Redis
- **Containerization:** Docker
- **CI/CD:** GitHub Actions (or other pipelines)

## 👥 Team Roles

- **Backend Developer**  
  Responsible for building and maintaining the server-side logic, designing API endpoints, integrating third-party services, and ensuring the application is scalable and efficient.

- **Database Administrator (DBA)**  
  Designs, implements, and maintains the database schema. Handles indexing, optimization, backup strategies, and ensures data integrity and security.

- **DevOps Engineer**  
  Manages the deployment process, monitors server performance, sets up continuous integration/continuous deployment (CI/CD) pipelines, and ensures system scalability and reliability.

- **QA Engineer**  
  Ensures that all backend functionalities meet the project's requirements through thorough testing. Writes automated tests, performs manual testing, and reports bugs.

- **Project Manager (optional addition)**  
  Coordinates between different roles, ensures timelines are met, manages communication, and tracks project progress.

## 🗄️ Database Design

### Key Entities:

#### 1. Users
- **id**: Primary Key
- **username**: Unique username
- **email**: Unique email address
- **password**: Hashed password
- **date_joined**: Timestamp of registration
- **role**: (e.g., Host, Guest)

#### 2. Properties
- **id**: Primary Key
- **owner_id**: Foreign Key to Users (Host)
- **title**: Property title
- **description**: Property description
- **location**: Property address or coordinates
- **price_per_night**: Rental price per night

#### 3. Bookings
- **id**: Primary Key
- **property_id**: Foreign Key to Properties
- **user_id**: Foreign Key to Users (Guest)
- **check_in_date**: Start date of booking
- **check_out_date**: End date of booking
- **status**: (e.g., Confirmed, Cancelled)

#### 4. Payments
- **id**: Primary Key
- **booking_id**: Foreign Key to Bookings
- **amount**: Payment amount
- **payment_date**: Timestamp of payment
- **payment_status**: (e.g., Paid, Pending)

#### 5. Reviews
- **id**: Primary Key
- **property_id**: Foreign Key to Properties
- **user_id**: Foreign Key to Users (Guest)
- **rating**: Numerical rating (e.g., 1-5)
- **comment**: Text review
- **created_at**: Timestamp of review

### Relationships:
- A **User** can create multiple **Properties** (1-to-Many).
- A **Property** can have multiple **Bookings** (1-to-Many).
- A **Booking** belongs to one **User** (Guest) and one **Property** (Many-to-1).
- A **Payment** is linked to a specific **Booking** (1-to-1).
- A **Review** is created by a **User** for a **Property** (Many-to-1).

## 🚀 Getting Started
Coming soon: Setup instructions, API usage, and deployment guides.

---

