# Airbnb Clone Backend

## 🚀 Project Overview

The **Airbnb Clone Backend** is a server-side application that powers an Airbnb-like property rental platform. It supports user registration, property listings, booking processes, payment management, and reviews, with secure APIs built using Django and PostgreSQL. This backend is designed to be scalable, secure, and efficient for production use.

---

## 🎯 Project Goals

- Enable users to sign up, log in, and manage profiles securely.
- Allow hosts to list and manage rental properties.
- Let guests browse properties and make bookings.
- Handle payments securely through integrated gateways.
- Support reviews for transparency and reputation management.
- Provide efficient, maintainable, and testable backend logic.
- Automate deployment and testing via CI/CD pipelines.

---

## 👥 Team Roles

| Role                    | Responsibility                                                                 |
|-------------------------|----------------------------------------------------------------------------------|
| **Project Manager**     | Coordinates tasks, timelines, and deliverables.                                 |
| **Product Owner**       | Defines scope, prioritizes features, and ensures business alignment.            |
| **Backend Developer**   | Builds APIs, integrates services, and manages server-side logic.                |
| **Frontend Developer**  | Connects backend APIs to client-facing UI.                                      |
| **Database Administrator (DBA)** | Designs and maintains database schemas, indexing, and optimizations.       |
| **DevOps Engineer**     | Automates testing, deployment, and infrastructure using CI/CD.                  |
| **QA Engineer**         | Conducts functional and automated tests.                                        |
| **UI/UX Designer**      | Designs wireframes and improves user experience and accessibility.              |

---

## 🧰 Technology Stack

| Technology             | Purpose                                                                 |
|------------------------|-------------------------------------------------------------------------|
| **Django**             | Python web framework for building scalable backend logic and APIs.      |
| **Django REST Framework** | For developing robust and secure REST APIs.                              |
| **PostgreSQL**         | Relational database for storing structured app data.                    |
| **GraphQL**            | Query language for efficient data retrieval by frontend clients.        |
| **Celery**             | Asynchronous task queue for background jobs (e.g., emails, reminders).  |
| **Redis**              | In-memory data store used as a task broker for Celery and caching.      |
| **Docker**             | Containerization for consistent development and production environments.|
| **GitHub Actions**     | CI/CD tool for automating tests, builds, and deployments.               |

---

## 🗃️ Database Design

### 🧑 Users
- `user_id`: Unique identifier  
- `name`: Full name  
- `email`: Email address (unique)  
- `password_hash`: Securely stored password  
- `role`: Guest or Host  

### 🏠 Properties
- `property_id`: Unique identifier  
- `host_id`: References the host (user_id)  
- `title`: Name/title of the listing  
- `description`: Property description  
- `location`: Address or coordinates  

### 📅 Bookings
- `booking_id`: Unique identifier  
- `property_id`: References booked property  
- `guest_id`: References the guest (user_id)  
- `start_date`: Check-in date  
- `end_date`: Check-out date  
- `total_price`: Final booking price  

### 💳 Payments
- `payment_id`: Unique identifier  
- `booking_id`: References the booking  
- `amount`: Paid amount  
- `payment_method`: Card, PayPal, etc.  
- `status`: Payment status (success/failure)  

### 🌟 Reviews
- `review_id`: Unique identifier  
- `property_id`: References the property  
- `guest_id`: References the reviewer  
- `rating`: Score from 1 to 5  
- `comment`: Written feedback  

### 🔄 Entity Relationships

- One **user** can have many **properties** (if they are a host).
- One **property** can have many **bookings**.
- One **booking** has one **payment**.
- One **guest** can leave multiple **reviews** for different **properties**.

---

## 🛠️ Feature Breakdown

- ✅ **User Management**: Registration, login, JWT auth, and profile editing.
- 🏘️ **Property Management**: CRUD operations for hosts to list and update properties.
- 📆 **Booking System**: Date selection, availability checks, price calculation.
- 💰 **Payment Gateway**: Integration with payment processors for secure checkout.
- 🌟 **Review System**: Guests can review and rate properties.
- 📡 **Admin Dashboard**: Admins manage users, properties, and reported content.
- 🔍 **Search & Filter**: Browse properties based on location, date, and price.

---

## 🔐 API Security

Security measures implemented:

- **JWT Authentication**: Secure token-based login system.
- **Role-Based Access Control**: Separate privileges for guests, hosts, and admins.
- **Rate Limiting**: Prevents abuse of API endpoints.
- **Input Validation**: Prevents XSS and SQL injection.
- **HTTPS Enforcement**: Secure communication with SSL.

---

## 📈 CI/CD Pipeline

### 🧠 What is CI/CD?

**CI/CD (Continuous Integration and Continuous Deployment)** is a development strategy that automates the process of:

- **CI**: Automatically testing new code every time a change is pushed.
- **CD**: Automatically deploying new, tested code to production or staging.

### 🛠 Tools Used

| Tool              | Purpose                                                                      |
|-------------------|------------------------------------------------------------------------------|
| **GitHub Actions**| Runs unit tests, linting, and triggers builds on every push or pull request.|
| **Docker**        | Ensures the app runs identically across local dev, staging, and production. |
| **Celery + Redis**| Handles background jobs, improves scalability and performance.               |

### ✅ Benefits

- **Faster Deployment**: Push code confidently with automated deployment.
- **Automated Testing**: Catch bugs before they reach production.
- **Reduced Manual Work**: Developers focus on code, not server setups.
- **Improved Reliability**: Stable deployments reduce downtime and risk.

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for full details.

---

## 📬 Contact

Have questions or suggestions? Feel free to open an issue or submit a pull request.
