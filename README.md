# AirBnB Clone

## Objective:
The backend for the Airbnb Clone project is designed to provide a robust and scalable foundation for managing user interactions, property listings, bookings, and payments.   
This backend will support various functionalities required to mimic the core features of Airbnb, ensuring a smooth experience for users and hosts.  


## Project Goals:
1.**User Management:** Implement a secure system for user registration, authentication, and profile management.    
2.**Property Management:** Develop features for property listing creation, updates, and retrieval.  
3.**Booking System:** Create a booking mechanism for users to reserve properties and manage booking details.    
4.**Payment Processing:** Integrate a payment system to handle transactions and record payment details.  
5.**Review System:** Allow users to leave reviews and ratings for properties.  
6.**Data Optimization:** Ensure efficient data retrieval and storage through database optimizations.  


## Technology Stack:
1.**Django:** A high-level Python web framework used for building the RESTful API.  
2.**Django REST Framework:** Provides tools for creating and managing RESTful APIs.  
3.**PostgreSQL:** A powerful relational database used for data storage.  
4.**GraphQL:** Allows for flexible and efficient querying of data.  
5.**Celery:** For handling asynchronous tasks such as sending notifications or processing payments.  
6.**Redis:** Used for caching and session management.  
7.**Docker:** Containerization tool for consistent development and deployment environments.  
8.**CI/CD Pipelines:** Automated pipelines for testing and deploying code changes.  


## Team Roles:
1.**Backend Developer:** Responsible for implementing API endpoints, database schemas, and business logic.  
2.**Database Administrator:** Manages database design, indexing, and optimizations.  
3.**DevOps Engineer:** Handles deployment, monitoring, and scaling of the backend services.  
4.**QA Engineer:** Ensures the backend functionalities are thoroughly tested and meet quality standards.  

## Technology Stack:
1.**Django:** A high-level Python web framework used for building the RESTful API.  
2.**Django REST Framework:** Provides tools for creating and managing RESTful APIs.  
3.**PostgreSQL:** A powerful relational database used for data storage.  
4.**GraphQL:** Allows for flexible and efficient querying of data.  
5.**Celery:** For handling asynchronous tasks such as sending notifications or processing payments.  
6.**Redis:** Used for caching and session management.  
7.**Docker:** Containerization tool for consistent development and deployment environments.  
8.**CI/CD Pipelines:** Automated pipelines for testing and deploying code changes.  

## Database Design:

## Users: 

### Key Fields:
**id:** Unique identifier for each user  
**name:** Full name of the user  
**email:** Unique email address used for authentication  
**password:** Hashed password for secure login  
**role:** Defines whether the user is a guest or host  

### Relationships:
A user can own multiple properties.  
A user can make multiple bookings.  
A user can write multiple reviews.  

## Properties:

### Key Fields:
**id:** Unique property identifier  
**owner:** Foreign key referencing the user who owns the property  
**title:** Property name or listing title  
**location:** Address or city where the property is located  
**price_per_night:** Nightly rate for booking  

### Relationships:
A property belongs to one user (host).    
A property can have multiple bookings.  


## Bookings:

### Key Fields:

**id:** Unique booking identifier    
**user:** Foreign key referencing the user who made the booking    
**property:** Foreign key referencing the booked property     
**check_in_date:** Start date of the booking    
**check_out_date:** End date of the booking    

### Relationships:

A booking belongs to one user and one property.  
A booking can be linked to a single payment.  


## Reviews:

### Key Fields:

**id:** Unique review identifier  
**user:** Foreign key referencing the reviewer  
**property:** Foreign key referencing the reviewed property  
**rating:** Numeric score (1–5)  
**comment:**User feedback text  

### Relationships:

A review belongs to one user and one property.
A property can have multiple reviews from different users.

## Payments:

### Key Fields:

**id:** Unique payment identifier
**booking:** Foreign key referencing the booking being paid for
**amount:** Payment amount
**status:** Payment state (e.g., pending, completed, failed)
**transaction_date:** Date and time of payment

### Relationships:
A payment belongs to one booking.
A booking has one corresponding payment record.


## Entity Relationships Summary:
User → Property: **One-to-Many**
User → Booking: **One-to-Many**
Property → Booking: **One-to-Many**
Property → Review: **One-to-Many**
Booking → Payment: **One-to-One**