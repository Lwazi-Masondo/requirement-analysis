# Requirement Analysis in Software Development.

Welcome! This repository explores the concept and relevance of requirement analysis in the software development life cycle. Requirement analysis focuses on understanding the intended functions of a software product and the limitations it must work within. It is typically a collaborative and technical process where developers and stakeholders work together to define the goals and constraints of a new or modified software system. This involves gathering, documenting, and evaluating business needs to ensure they are clear, achievable, and well-understood.

## What is Requirement Analysis?

Requirement Analysis is a critical phase in the Software Development Life Cycle (SDLC) that involves identifying, gathering, and analyzing the needs and expectations of stakeholders for a proposed software system. The primary goal of this process is to clearly understand what the software must do (functional requirements) and the conditions it must meet (non-functional requirements), such as performance, security, and usability. This process is typically a collaborative effort between business analysts, stakeholders, project managers, and software developers. It serves as the foundation for all subsequent phases of the SDLC, ensuring that the final product aligns with business goals and user needs.

## Why is Requirement Analysis Important?

1. All stakeholders will have a clear detailed understanding and expectation of the software as well as the basis of its design.
2. The scope of the software project will be clearly defined, preventing scope creep.
3. It facilitates accurate estimation of the amount of time and money that needs to be invested in the project.

## Key Activities in Requirement Analysis.

#### 1. Requirement Gathering 

This involves conducting interviews, surveys, workshops, observation and document analysis. Each of these methods are aimed at gathering information in order to undertstand stakeholder requirements and current system functionalities.

#### 2. Requirement Elicitation 

Requirements can be gathered by brainstorming ideas, engaging focus groups for in-depth input, and using prototypes to help stakeholders visualize and refine their needs.

#### 3. Requirement Documentation 

Requirements are documented through detailed specification documents, user stories describing functionality from the user's viewpoint, and use case diagrams illustrating system-user interactions.

#### 4. Requirement Analysis and Modeling

Requirements are evaluated by prioritizing them, analyzing their feasibility, and using models to visualize and better understand them.

#### 5. Requirement Validation

Requirements are validated through stakeholder reviews, defined acceptance criteria, and traceability to ensure completeness and alignment throughout development.

## Types of Requirements.

### Functional Requirements
Functional requirements define what the system should do—the features, behaviors, and functions expected by the user.

**User Registration and Login**
Users (customers or hotel managers) must be able to sign up, log in, and access their respective dashboards.
*Example: Hotel managers log in to update room availability; customers log in to view their booking history.*

**Hotel Listing Management**
Hotel managers must be able to add, update, or remove hotel and room details.
*Example: A hotel owner updates the room price or availability through the Hotel Management Service.*

**Search Functionality**
Customers must be able to search for hotels based on filters like location, price, and ratings.
*Example: The system uses Elasticsearch to fetch hotel listings that match the user’s criteria.*

**Booking Process**
Users must be able to select a hotel, book a room, and receive booking confirmation.
*Example: A customer books a hotel, and the system updates the booking database and sends a confirmation.*

**Payment Integration**
The system must support secure online payments via third-party payment services.
*Example: The booking service interacts with an external payment gateway to complete transactions.*

**Notification Service**
The system must notify users about bookings, cancellations, or new offers.
*Example: Kafka triggers a notification to the hotel manager when a new booking is made.*

**View Past and Current Bookings**
Customers and managers should be able to view booking history and active reservations.
*Example: Booking details are fetched from Redis (for recent data) or Cassandra (for archived data).*

### Non-Functional Requirements
Non-functional requirements describe how the system performs and the constraints under which it must operate.

**Performance and Scalability**
The system must handle high traffic and large volumes of data efficiently.
*Example: Microservice architecture and database replication (master-slave DB, Redis caching) ensure performance at scale.*

**Availability and Reliability**
The system must be available to users 24/7 without downtime.
*Example: Load balancers and service clusters ensure continuous availability even under load.*

**Responsiveness**
System APIs must respond quickly to user actions.
*Example: Redis is used to cache recent data, reducing database queries and speeding up response time.*

**Data Consistency and Synchronization**
All changes in data must be consistently updated across services.
*Example: Data updates are sent to messaging queues and synchronized across services (e.g., ElasticSearch and Cassandra).*

**Security**
User data, payment details, and personal information must be securely handled.
*Example: Secure third-party payment integration and restricted access to different user roles.*

**Maintainability and Modularity**
The system should be easy to update and maintain.
*Example: Microservices allow individual components (e.g., booking, search, notifications) to be updated independently.*

**Archival and Data Management**
Old booking data must be archived for performance and reporting.
*Example: Apache Kafka streams booking data to Hadoop for long-term storage and analysis.*

## Use Case Diagrams.

Use Case Diagrams are a type of Unified Modeling Language (UML) diagram used to visually represent the interactions between users (actors) and a system to achieve specific goals. They illustrate what the system will do from the user's perspective, without going into how it will be implemented.

In a use case diagram:

* **Actors** represent users or external systems interacting with the software.

* **Use Cases** are specific functions or services the system performs in response to user actions.

* **System Boundaries** define the scope of the system being modeled.

### Benefits of Use Case Diagrams in Requirement Analysis

**Clarify Functional Requirements**
They provide a clear overview of system functionality and user interactions, helping teams understand what the system needs to do.

**Promote Stakeholder Communication**
Use case diagrams are simple and visual, making it easier for both technical and non-technical stakeholders to collaborate and give feedback.

**Define System Scope**
They help in identifying the system’s boundaries and what lies outside its scope, preventing scope creep.

**Identify Primary and Secondary Users**
By outlining all actors, teams can understand who the key users are and what actions they will perform.

**Support Test Case Development**
Each use case can be used to generate specific test scenarios, ensuring comprehensive test coverage.

**Aid in Project Planning**
Use cases help prioritize development tasks based on which user interactions are most critical.

#### Example Use Case in a Hotel Booking System:
**Use Case:** Book a Hotel Room

**Actors:** Customer, Payment Gateway

**Use Cases:** Search Hotels, Select Room, Enter Guest Details, Make Payment, Receive Confirmation

**Use Case Diagram**
**alx-booking-uc.png:** https://drive.google.com/file/d/17QQa98_Kid5R666ohULjNo-EKzWTKsSx/view?usp=sharing 


## Acceptance Criteria.

Acceptance criteria are specific, predefined conditions that a software feature must meet to be accepted by stakeholders, product owners, or end-users. They are crucial in the requirement analysis phase because they translate broad user needs into clear, testable expectations. This ensures all stakeholders have a shared understanding of what "done" means for a given feature.

### Why Acceptance Criteria Matter:

**Clarify Requirements:** They eliminate ambiguity by detailing exactly what the feature should do and under what conditions.

**Guide Development:** Developers use them to understand what functionality needs to be built and how it should behave.

**Support Testing:** QA teams create test cases based on acceptance criteria, ensuring the feature meets business and user expectations.

**Prevent Scope Creep:** Clear boundaries help prevent additional features from being added without proper review or planning.

**Improve Stakeholder Communication:** They serve as a contract between stakeholders and the development team, aligning expectations.

*Example: Acceptance Criteria for Checkout Feature in a Booking Management System*
*Feature: Checkout Process for Hotel Booking*

**Acceptance Criteria:**

1. User must be able to review selected hotel details and total price before confirming the booking.

2. Checkout must include fields for customer details (name, email, phone) and payment information.

3. System must validate all required fields before proceeding to payment.

4. User must be redirected to a secure payment gateway for processing.

5. Upon successful payment, the system must generate a booking confirmation and display it to the user.

6. A confirmation email must be sent to the customer with booking and payment details.

7. The booking data must be stored in the booking database and cached for quick access.

