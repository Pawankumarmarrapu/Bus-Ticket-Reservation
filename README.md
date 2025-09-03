# Bus Ticket Reservation Management System

A comprehensive, production-ready **Bus Ticket Booking System** built with:

**Backend** → Java (Spring Boot, Spring Security, JWT, MySQL, JPA/Hibernate, Swagger)  
**Frontend** → React.js (Hooks, Router, Axios, Bootstrap, Formik + Yup)  

This project provides a **complete solution** for online bus ticket booking with **real-time seat availability, bookings, cancellations, payments, and admin management**.

## Features

### User Authentication & Roles
- User Registration & Login with **JWT authentication**  
- Role-based Access → **Admin** and **Customer**  
- Secure API authorization  

### Customer Features
- Search trips by **origin, destination, and date**  
- Real-time **seat selection** with seat map  
- Passenger details form with validation (**Formik + Yup**)  
- Booking creation, payment, and e-ticket generation (PDF/QR)  
- Cancel bookings with refund policy  
- Notifications via **Email/SMS**  

### Admin Features
- Manage **buses, routes, and seat layouts**  
- Create and schedule trips, assign fares  
- Cancel trips and manage seat inventory
- 
## 🛠 Technology Stack
### Backend
- Java 17+, Spring Boot, Spring Security (JWT)  
- MySQL (Database)  
- JPA / Hibernate (ORM)  
- Swagger / OpenAPI (API Docs)  
- BCrypt (Password Security)  

### Frontend
- React (Functional Components + Hooks)  
- React Router (Navigation)  
- Axios (API Calls)  
- Formik + Yup (Form Validation)  
- Bootstrap + CSS (Responsive UI)  

### Architecture
 **REST API** (secured with JWT)  
 **Microservices Ready**: Separate services for User, Bus/Route, Trip, Booking, and Payments  
 **Service Discovery** with **Eureka Server** (if deployed in microservices)  

##  Project Structure

/backend
  
   ─ user-service        # Authentication, user roles
   
   ─ busroute-service    # Bus & route management
   
   ─ trip-service        # Trip scheduling, fares, seat inventory
   
   ─ booking-service     # Booking, payments, cancellations
   
   ─ eureka-server       # Service discovery
   
/frontend
  
   ─ public/             # Static assets
   
   ─ src/                # React components, routes, services
   
   ─ package.json        # Dependencies
   
/docs
 
   ─ Bus Ticket Reservation Management.pdf
   

##  Getting Started

### Prerequisites
- JDK 17 or higher  
- Node.js v16+  
- MySQL Server (running locally)  
- Maven (for building backend)  

### Backend Setup

***bash
# Clone repo
git clone https://github.com/Pawankumarmarrapu/Bus-Ticket-Reservation
cd bus-ticket-booking/backend

# Create MySQL Database
CREATE DATABASE busbooking;

# Update database credentials
# In each service's application.properties

# Run microservices one by one
cd user-service
mvn spring-boot:run

cd ../busroute-service
mvn spring-boot:run

cd ../trip-service
mvn spring-boot:run

cd ../booking-service
mvn spring-boot:run

cd ../eureka-server
mvn spring-boot:run
```

Swagger API Docs available at:  
  "http://localhost:8080/swagger-ui/"

##  Frontend Setup

***bash
cd ../frontend
npm install
npm start

Now open "http://localhost:3000" in your browser.  

##  Usage
### For Customers
1. Register & login  
2. Search buses by route and date  
3. Pick available seats (real-time updates)  
4. Enter passenger details & confirm booking  
5. Download **e-ticket (PDF/QR)**  
6. Cancel if needed (refund policy applies)  

### For Admins
1. Login as Admin  
2. Add/manage buses, routes, and trips  
3. Set fares and schedules  
4. Cancel/manage bookings and trips  
5. View revenue, sales, and occupancy reports  

## Booking Flow

1. **Search** buses → by origin, destination, date, bus type  
2. **Select trip** → view real-time seat availability  
3. **Choose seats** → interactive seat map  
4. **Enter passenger details**  
5. **Confirm booking & payment**  
6. **E-ticket generated** → download PDF/QR  
7. **Admin management** → cancellations, reports  

## Database Design (Simplified)

- **User**: id, name, email, phone, password, role  
- **Bus**: id, busNumber, type (AC/Non-AC), totalSeats, operator  
- **Route**: id, source, destination, distance, duration  
- **Trip**: id, busId, routeId, departure, arrival, fare  
- **Seat**: id, tripId, seatNumber, type, isBooked  
- **Booking**: id, userId, tripId, bookingDate, totalAmount, status  
- **Payment**: id, bookingId, status, transactionRef 

## License
Capstone Project.  

## Author
Developed by **Marrapu Pawankumar** 
