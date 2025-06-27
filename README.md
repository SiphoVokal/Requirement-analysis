# Requirement Analysis in Software Development

## What is Requirement Analysis?

Requirement analysis is the process of gathering, analyzing and defining the requirements of the software product to be developed, it involves communicating with all the stakeholders involved in the project to understand what the system is expected to do and how it should perform.


## Why is Requirement Analysis Important?

1. Clarity and Understanding - 
It helps in understanding what the stakeholders expect from the software, reducing ambiguity.

2. Scope Definition - 
Clearly defines the scope of the project, which helps in preventing scope creep.

3. Basis for Design and Development - 
Provides a solid foundation for designing and developing the system.

4. Cost and Time Estimation - 
Facilitates accurate estimation of project cost, resources, and time.

5. Quality Assurance - 
Ensures that the final product meets the specified requirements, leading to higher customer satisfaction.

## Key Activities in Requirement Analysis

1. Requirement Gathering 
  * Interviews: Conducting interviews with stakeholders to gather detailed information about their needs and expectations.
  * Surveys/Questionnaires: Distributing surveys to collect requirements from a larger audience.
  * Workshops: Organizing workshops with stakeholders to discuss and gather requirements.
  * Observation: Observing end-users in their working environment to understand their needs.
  * Document Analysis: Reviewing existing documentation and systems to understand current functionalities and requirements.
  
2. Requirement Elicitation 
* Brainstorming: Conducting brainstorming sessions to generate ideas and gather requirements.
* Focus Groups: Holding focus group discussions with selected stakeholders to gather detailed requirements.
* Prototyping: Creating prototypes to help stakeholders visualize the system and refine their requirements.

3. Requirement Documentation 
* Requirement Specification Document: Creating a detailed document that lists all functional and non-functional requirements.
* User Stories: Writing user stories to describe functionalities from the user’s perspective.
* Use Cases: Creating use case diagrams to show interactions between users and the system.

4. Requirement Analysis and Modeling 
* Requirement Prioritization: Prioritizing requirements based on their importance and impact on the project.
* Feasibility Analysis: Assessing the feasibility of requirements in terms of technical, financial, and time constraints.
* Modeling: Creating models (e.g., data flow diagrams, entity-relationship diagrams) to visualize and analyze requirements.

5. Requirement Validation 
* Review and Approval: Reviewing the documented requirements with stakeholders to ensure accuracy and completeness.
* Acceptance Criteria: Defining clear acceptance criteria for each requirement to ensure they meet the expected standards.
* Traceability: Establishing traceability matrices to ensure all requirements are addressed during development and testing.

## Types of Requirements

### 1. Hotel Management Service
(Used by hotel managers to onboard properties and manage inventory)

**Functional Requirements**

* Onboard and manage hotels: Managers can register hotel details (name, location, images) and update them via a management portal 
* Manage room types and rooms: Add/update/delete room types (e.g., Deluxe Suite) and individual rooms under those types 
* Define pricing and inventory: Set prices and available room counts per day per room type 

**Non‑Functional Requirements**

* High consistency: Write operations (e.g., inventory updates) must reliably sync to the master DB so that search and booking services reflect accurate data 
* Availability & low latency: Manager APIs should be responsive and accessible even during peak times 
* Scalability: Services must handle increasing numbers of hotel accounts, new properties, and metadata 

### 2. Customer Service – Search & Booking
(Used by guests to find and reserve rooms)

**Functional Requirements**

* Search hotels: Users can search by location, dates, price range, amenities 
* View room details: Retrieve info on available room types, pricing, images, description 
* Real‑time availability check: System verifies that requested rooms are still available before confirming booking 
* Booking engine: Users select room type/dates, confirm booking, and receive notifications 
* Payment processing: Integrate with third‑party payment service for secure transactions 
* Prevent double bookings: Ensure concurrency control so two users can’t reserve the same room simultaneously 


**Non‑Functional Requirements**

* Low latency searches: Fast responses (<100–500 ms) for search operations 
* High availability & scalability: 99.99% uptime; ability to scale for surges (e.g., holiday season) 
* Strong consistency during booking: Booking and inventory updates must be atomic to avoid overbooking 
* High concurrency handling: Must support thousands of simultaneous booking requests 
* Reliability: Ensure booking requests do not fail silently and maintain data integrity 

### 3. View Booking Service
(Displays booking history to customers and managers)

**Functional Requirements**

* View current bookings: Show ongoing reservations with full details
* View past bookings: Access archived or canceled bookings 
* Filter & search bookings: Users can query by date range, status, property 

**Non‑Functional Requirements**

* Low latency: Use of caching (like Redis) ensures fast load times for viewing bookings 
* Read scalability: Must efficiently serve both active and archived booking data from SQL and Cassandra 
* Consistency between caches: Data across Redis, MySQL, and Cassandra should stay in sync 

### 4. Final Design – Notification & Analytics

**Functional Requirements**

* Notifications: Notify users/managers on booking confirmations, cancellations, offers 
* Data analytics & big‑data ingestion: Process event streams (e.g., bookings, searches) for insights, recommendations, dynamic pricing 

**Non‑Functional Requirements**

* Eventual consistency: Services like Elasticsearch, Hadoop, and analytics systems must reflect events timely despite being asynchronous 
* Throughput & fault-tolerance: Messaging components (Kafka, consumers) should handle high event volumes with high availability
* Scalability: Analytics and notification systems must dynamically scale during peaks

## Use Case Diagrams

Use case diagrams show how different users (actors) interact with the system to achieve specific goals (use cases)

### Benefits of Use Case Diagrams

* Provide a clear visual representation of system functionalities.
* Help in identifying and organizing system requirements.
* Facilitate communication among stakeholders and development team.

![alx-booking-uc](https://github.com/user-attachments/assets/b2ff8422-ec4a-4184-a29f-68252e003ecd)


## Acceptance Criteria

Acceptance criteria are conditions that a feature must meet to be accepted by the stakeholders, for example users should be able to make a payment on the management system after choosing a hotel room.
