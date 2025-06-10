# ✈️ Airline Ticketing and Management System

## 🔍 Overview

This project is a comprehensive database-backed web application that simulates an airline's ticketing and management system. It supports secure, role-specific access for **customers**, **booking agents**, and **airline staff**, each equipped with features such as ticket search and purchase, flight status updates, commission tracking, and reporting.


## 🧠 Features by Role

### 🧾 Public Users
- **Search Flights**: Search upcoming flights by flight number or city/date.
- **Dynamic Filters**: Smart dropdown search boxes update with input.

### 👤 Customers
- **View My Flights**: List all upcoming purchased flights.
- **Purchase Tickets**: Search and purchase future flights.
- **Track Spending**: View monthly spending for past 6 months in bar chart.
- **Purchase Rules**: Prevents buying past flights or using invalid emails.

### 💼 Booking Agents
- **View My Flights**: View flights booked through agent account.
- **Purchase for Clients**: Purchase tickets on behalf of customers.
- **My Commission**: Track total commissions and tickets sold.
- **Top Customers**: View customers by tickets or commissions.

### 🛫 Airline Staff
- **View/Update Flights**: View and update status of flights in the next 30 days.
- **Manage Flights**: Create flights, airplanes, airports.
- **Agent Overview**: View top agents by commission or ticket count.
- **Frequent Flyers**: View most frequent customers over past year.
- **Reports**:
- **Monthly ticket sales**
- **Revenue breakdown: direct vs. indirect**
- **Top destinations**


## 🛡️ Security Features

- **Identity Enforcement**: Restricts access to correct role-based views.
- **Logout Protection**: Prevents back-button access to protected pages.
- **Input Validation**:
- **Invalid emails block agent purchases**
- **Flight status updates validated**


## 🗃️ Sample SQL Queries

Examples of functionality powered by SQL:

- **Search Upcoming Flights**
```sql
SELECT DISTINCT f.airline_name, f.flight_num, a.airport_city, ...
FROM flight f
JOIN ticket USING (flight_num)
JOIN purchases p USING (ticket_id)
JOIN airport a ON a.airport_name = f.departure_airport
JOIN airport b ON b.airport_name = f.arrival_airport
WHERE f.departure_time >= '{start_date}' AND f.departure_time <= '{end_date}';
```

## 🧩 Security Features

- **Role-based session expiration**
- **Notification system for flight changes**
- **Payment integration**
- **Real-time seat availability**

