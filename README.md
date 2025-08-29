# Airbnb Clone Project

## Overview
The Airbnb Clone Project aims to replicate core functionalities of the Airbnb platform, allowing users to list, discover, and book accommodations. The project goals include building a scalable web application with a user-friendly interface, secure backend APIs, and efficient database management to handle user interactions, property listings, and bookings.

## Team Roles
- **Frontend Developer**: Responsible for designing and implementing the user interface using React, ensuring a responsive and intuitive experience for users browsing properties and managing bookings.
- **Backend Developer**: Builds and maintains the server-side logic using Django, creating RESTful APIs to handle requests and ensure seamless communication between the frontend and database.
- **Database Administrator**: Designs and optimizes the PostgreSQL database schema, ensuring data integrity and efficient querying for entities like users, properties, and bookings.
- **DevOps Engineer**: Sets up and manages the CI/CD pipeline using tools like GitHub Actions and Docker, automating deployments and ensuring system reliability.
- **Quality Assurance Engineer**: Tests the application to identify bugs and ensure features like booking and payment systems function correctly across different scenarios.

## Technology Stack
- **Django**: A Python web framework used for building robust RESTful APIs to handle backend logic and data processing.
- **PostgreSQL**: A relational database management system for storing and managing data related to users, properties, bookings, and payments.
- **React**: A JavaScript library for building a dynamic and responsive user interface for the web application.
- **GraphQL**: A query language for APIs, enabling efficient data retrieval by allowing clients to request only the data they need.
- **Docker**: A containerization platform used to package the application and its dependencies for consistent deployment across environments.

## Database Design
- **Users**:
  - Fields: `user_id` (primary key), `email`, `password_hash`, `name`, `phone_number`
  - Relationships: A user can own multiple properties and make multiple bookings.
- **Properties**:
  - Fields: `property_id` (primary key), `owner_id` (foreign key to Users), `title`, `description`, `price_per_night`, `location`
  - Relationships: A property belongs to one user and can have multiple bookings and reviews.
- **Bookings**:
  - Fields: `booking_id` (primary key), `property_id` (foreign key to Properties), `user_id` (foreign key to Users), `check_in_date`, `check_out_date`
  - Relationships: A booking is associated with one property and one user.
- **Reviews**:
  - Fields: `review_id` (primary key), `property_id` (foreign key to Properties), `user_id` (foreign key to Users), `rating`, `comment`
  - Relationships: A review is linked to one property and one user.
- **Payments**:
  - Fields: `payment_id` (primary key), `booking_id` (foreign key to Bookings), `amount`, `payment_date`, `status`
  - Relationships: A payment is tied to one booking.

## Feature Breakdown
- **User Management**: Allows users to register, log in, and manage their profiles, ensuring secure access to the platform and personalized experiences.
- **Property Management**: Enables hosts to list properties, update details, and manage availability, forming the core of the accommodation offerings.
- **Booking System**: Facilitates users booking properties for specific dates, handling availability checks and confirmation, critical for user transactions.
- **Review System**: Allows users to leave ratings and comments on properties, enhancing trust and decision-making for future bookings.
- **Payment Processing**: Integrates secure payment gateways to handle transactions, ensuring safe and reliable financial operations.

## API Security
- **Authentication**: Implements JWT (JSON Web Tokens) to verify user identity, protecting user accounts and preventing unauthorized access.
- **Authorization**: Uses role-based access control to restrict actions (e.g., only property owners can edit listings), safeguarding data integrity.
- **Rate Limiting**: Limits API request rates to prevent abuse and ensure fair usage, maintaining system performance and availability.
- **Data Encryption**: Employs HTTPS and encrypted database storage to protect sensitive data like user information and payment details, crucial for user trust and compliance.
- **Input Validation**: Sanitizes and validates all user inputs to prevent injection attacks, ensuring the application remains secure against common vulnerabilities.

## CI/CD Pipeline
CI/CD pipelines automate the process of integrating, testing, and deploying code changes, ensuring faster and more reliable development cycles. For this project, tools like **GitHub Actions** can be used to run automated tests and linting on each commit, while **Docker** ensures consistent environments for building and deploying the application. This setup reduces manual errors, improves collaboration, and enables rapid delivery of updates.
