# RaceDay Database Management System

## Project Overview

RaceDay is a relational database management project designed to manage sporting events such as marathons, running races, and cycling events. The database stores and organizes information about event organizers, events, categories, participants, registrations, results, weather conditions, and routes.

The project uses Microsoft SQL Server and T-SQL to create and manage the database.

## Objectives

- Store event organizer details.
- Manage sporting events and their locations.
- Organize event categories and distances.
- Store participant information.
- Manage participant registrations.
- Record race results and finishing positions.
- Store event weather forecasts and route information.
- Maintain data integrity using primary keys, foreign keys, and constraints.

## Technologies Used

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)
- SQL (T-SQL)

## Database Tables

The database consists of the following tables:

| Table | Description |
|---|---|
| `EVENT_ORGANIZER` | Stores event organizer details. |
| `EVENT` | Stores event names, dates, locations, and descriptions. |
| `CATEGORY` | Stores event categories, distances, and participant limits. |
| `PARTICIPANT` | Stores participant contact information. |
| `REGISTRATION` | Records participant registrations. |
| `RESULTS` | Stores finishing times, positions, and pace. |
| `WEATHER` | Stores weather information for events. |
| `ROUTE` | Stores event route details. |

## Database Relationships

The database uses primary keys and foreign keys to connect related tables and maintain data integrity.

- One organizer can manage multiple events.
- An event can have multiple categories.
- Participants can register for event categories.
- Registrations can have associated race results.
- Events can have associated weather records and routes.

## Database Constraints

The database uses the following constraints:

- **PRIMARY KEY:** Uniquely identifies each record.
- **FOREIGN KEY:** Connects related tables.
- **NOT NULL:** Ensures required fields contain values.
- **UNIQUE:** Prevents duplicate values where required.
- **CHECK:** Restricts values to valid options.
- **DEFAULT:** Supplies predefined values when applicable.
- **IDENTITY:** Automatically generates numeric identifiers where configured.

## Installation and Setup

### Requirements

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)

### Steps

1. Clone or download this repository.
2. Open SQL Server Management Studio.
3. Connect to your SQL Server instance.
4. Open the SQL scripts in the correct execution order.
5. Execute each script to create the database tables and relationships.
6. Run SQL queries to test the database.

### SQL Script Execution Order

Execute the scripts in the following order:

1. `01_EVENT_ORGANIZER.sql`
2. `02_EVENT.sql`
3. `03_CATEGORY.sql`
4. `04_PARTICIPANT.sql`
5. `05_REGISTRATION.sql`
6. `06_RESULTS.sql`
7. `07_WEATHER.sql`
8. `08_ROUTE.sql`

The order matters because some tables depend on other tables through foreign key relationships.

## Example SQL Queries

### Display All Events

```sql
SELECT *
FROM EVENT;
```

### Display Participants and Their Registrations

```sql
SELECT
    P.FirstName,
    P.LastName,
    R.RegistrationDate,
    R.RegistrationStatus
FROM PARTICIPANT P
JOIN REGISTRATION R
    ON P.ParticipantID = R.ParticipantID;
```

### Display Events and Their Categories

```sql
SELECT
    E.EventName,
    C.CategoryName,
    C.Distance,
    C.MaxParticipants
FROM EVENT E
JOIN CATEGORY C
    ON E.EventID = C.EventID;
```

## Sample Data

The database can be populated with sample sporting events, organizers, participants, registrations, race results, weather information, and routes for testing purposes.

## Project Purpose

This project demonstrates relational database design, table creation, SQL queries, primary and foreign key relationships, and the use of constraints to maintain data integrity.

## Author

**Wiseman-beem**

GitHub Repository: https://github.com/Wiseman-beem/RaceDay
