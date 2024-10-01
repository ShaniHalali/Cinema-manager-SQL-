#Cinema Management System🎥🎞️🎬🍿
This is the final assigment project for SQL course, in Afeka - the academic college of Engineering in Tel Aviv.

## Project Overview
The **Shani & Ori Cinema Management System** is a comprehensive solution designed to manage the operations of a cinema, including employee management, movie scheduling, and ticket sales for the viewers. The system efficiently organizes information related to movies, screenings, employees (ushers and ticket sellers), and cinema halls. It includes various SQL functionalities such as triggers, views, and functions to streamline cinema management.

## ERD Diagram
<img src="https://github.com/user-attachments/assets/57041d30-0189-4bda-b46a-4363c6d8c8d2" alt="WelcomePage" width="50%" height="50%">

## System Features
### 1. **Cinema Information**
- Each cinema has a unique ID and an address.
- Multiple halls with defined attributes: number of chairs, and an assigned usher.

### 2. **Employee Management**
- Employees include ushers and ticket sellers.
- Attributes include employee ID, name, gender, date of birth, and salary.
- Usher-specific data tracks the number of customers helped during screenings.
- Ticket seller-specific data tracks the number of tickets sold.

### 3. **Movie and Screening Management**
- Each movie has attributes such as ID, name, genre, rating, and duration.
- Each screening is associated with a specific movie and hall, with attributes including date and time.
- Screenings are dynamically managed, and available seats are calculated based on the number of sold tickets.

### 4. **Viewer and Ticket Management**
- Viewers can attend multiple screenings, and each screening can have multiple viewers.
- Each ticket has an ID, price, and category (Regular 40₪, Special 80₪, VIP 100₪).

## Key Functionalities
1. **Seat Availability Check**  
   - A function named `check_availability` ensures that before purchasing a ticket, seat availability is verified for the selected screening.

2. **Triggers**  
   - A trigger checks seat availability using the "check_availability" function before each ticket purchase.
   - A trigger is set up before any screening insert that activates the function "check_movie_screenings" to ensure that a specific movie does not have more than 2 screenings in one day.

3. **Data Management**  
   - Includes SQL queries for inserting new tickets, updating screening schedules, and deleting outdated or low-rated movies.

4. **Employee Bonus System**  
   - A query awards a salary bonus to outstanding employees (based on performance criteria like ticket sales and customer assistance).

5. **Views for Data Display**  
   - "employees_view": Displays employees' first names, last names, and roles, sorted alphabetically, excluding salary information, so that this information is not accessible to everyone..
   - "usherForHall_view" : Display the list of halls along with the name of the usher assigned to each hall.
   - "usherScreening_view": Shows ushers and their assigned screening shifts.
   - "CinemaOverview": Displays movie screenings, organized by title, date, time, and available seats.

6. **Revenue and Viewer Analytics**  
   - Queries to calculate total revenue from ticket sales and average viewers per movie.

## Database Tables
- **Cinema Table**: Holds basic cinema details.
- **Employee Tables**: Separate tables for ushers and ticket sellers, including their unique attributes.
- **Hall Table**: Includes hall details like number of rows and chairs.
- **Movie Table**: Stores information about each movie.
- **Screening Table**: Links movies to specific halls with date and time details.
- **Viewer and Ticket Tables**: Manages viewers and their purchased tickets.

## Users
- **Cinema Manager**: Manages screenings, employee performance, and revenue.
- **Employees**: Can view non-sensitive information about colleagues, track performance metrics and shifts .
- **Viewers**: Can purchase tickets and access relevant movie and screening details.

## SQL Highlights
- **Functions**: Implemented for seat availability checks and screening validation.
- **Triggers**: Used to automate seat checks before ticket purchases.
- **Views**: Various views to simplify data access for different users.
- **Aggregations**: Used for calculating revenue, average viewers, and sales performance.

