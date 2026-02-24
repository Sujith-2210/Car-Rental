# 🚗 Car Rental Application

A full-stack car rental management system built with **Spring Boot** (backend) and **React** (frontend). This application allows users to register, authenticate, browse available cars, and make bookings with real-time booking management.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Frontend Routes](#frontend-routes)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **User Authentication**: Register and login with JWT-based authentication
- **Car Management**: Browse and view available cars with details
- **Booking System**: Create, view, and manage car bookings
- **Admin Dashboard**: Manage bookings and update booking status
- **Role-Based Access Control**: Separate views for users and admins
- **Real-time Booking Status**: Update and track booking status
- **RESTful API**: Complete REST API for all operations
- **Responsive UI**: Modern, responsive frontend built with React and Vite

## 🛠️ Tech Stack

### Backend
- **Java 17+**
- **Spring Boot 3.x**
- **Spring Security with JWT**
- **Spring Data JPA**
- **MySQL Database**
- **Maven**

### Frontend
- **React 18+**
- **Vite**
- **Axios**
- **CSS3**
- **JavaScript ES6+**

## 📁 Project Structure

```
car-rental/
├── src/
│   ├── main/
│   │   ├── java/com/rental/car/
│   │   │   ├── CarApplication.java           # Main Spring Boot Application
│   │   │   ├── config/
│   │   │   │   ├── DataInitializer.java      # Database initialization
│   │   │   │   └── SecurityConfig.java       # Security configuration
│   │   │   ├── controller/
│   │   │   │   ├── AuthController.java       # Authentication endpoints
│   │   │   │   ├── BookingController.java    # Booking management
│   │   │   │   ├── CarController.java        # Car management
│   │   │   │   └── GlobalExceptionHandler.java
│   │   │   ├── dto/                          # Data Transfer Objects
│   │   │   ├── entity/                       # JPA Entities
│   │   │   ├── repository/                   # Data access layer
│   │   │   └── service/                      # Business logic
│   │   └── resources/
│   │       └── application.properties         # Application configuration
│   └── test/
│       └── CarApplicationTests.java           # Unit tests
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth.jsx                      # Login/Register component
│   │   │   ├── Cars.jsx                      # Car listing component
│   │   │   ├── Bookings.jsx                  # User bookings
│   │   │   └── AdminBookings.jsx             # Admin dashboard
│   │   ├── App.jsx                           # Main App component
│   │   ├── main.jsx                          # React entry point
│   │   ├── api.js                            # API client configuration
│   │   └── styles.css                        # Global styling
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
├── pom.xml                                    # Maven configuration
├── postman_collection.json                    # Postman API collection
└── README.md                                  # This file

```

## 📦 Prerequisites

- **Java**: JDK 17 or higher
- **Node.js**: v16 or higher
- **npm**: v7 or higher
- **Maven**: v3.6 or higher
- **MySQL**: v8.0 or higher

## 🚀 Installation

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Sujith-2210/Car-Rental.git
   cd Car-Rental
   ```

2. **Configure MySQL Database**
   - Create a MySQL database named `car_rental`
   - Update `src/main/resources/application.properties` with your database credentials:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/car_rental
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   ```

3. **Build the backend**
   ```bash
   mvn clean install
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API endpoint** (if needed)
   - Update `src/api.js` with your backend URL:
   ```javascript
   export const API_BASE_URL = 'http://localhost:8080/api';
   ```

## ▶️ Running the Application

### Start the Backend Server

```bash
mvn spring-boot:run
```
The backend server will start on `http://localhost:8080`

### Start the Frontend Development Server

```bash
cd frontend
npm run dev
```
The frontend will be available on `http://localhost:5173`

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/validate` - Validate JWT token

### Cars
- `GET /api/cars` - Get all available cars
- `GET /api/cars/{id}` - Get car by ID
- `POST /api/cars` - Create new car (Admin only)
- `PUT /api/cars/{id}` - Update car (Admin only)
- `DELETE /api/cars/{id}` - Delete car (Admin only)

### Bookings
- `GET /api/bookings` - Get all bookings for logged-in user
- `GET /api/bookings/{id}` - Get booking by ID
- `POST /api/bookings` - Create new booking
- `PUT /api/bookings/{id}` - Update booking status
- `DELETE /api/bookings/{id}` - Cancel booking

## 🌐 Frontend Routes

- `/` - Home/Cars listing
- `/login` - Login page
- `/bookings` - User bookings dashboard
- `/admin` - Admin bookings dashboard

## 🗄️ Database Schema

### Users Table
- `id` - Primary key
- `username` - Unique username
- `email` - User email
- `password` - Encrypted password
- `role` - USER or ADMIN

### Cars Table
- `id` - Primary key
- `model` - Car model
- `brand` - Car brand
- `year` - Manufacturing year
- `price_per_day` - Rental price
- `available` - Availability status

### Bookings Table
- `id` - Primary key
- `user_id` - Foreign key to Users
- `car_id` - Foreign key to Cars
- `start_date` - Booking start date
- `end_date` - Booking end date
- `status` - PENDING, CONFIRMED, CANCELLED

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💼 Author

**Sujith**
- GitHub: [@Sujith-2210](https://github.com/Sujith-2210)

## 🆘 Support

For support, please open an issue on the GitHub repository or contact the author.

---

**Happy Coding! 🎉**
