# Red Comunitaria - Community Network Platform

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3.5-brightgreen)
![Java](https://img.shields.io/badge/Java-17-blue)
![Docker](https://img.shields.io/badge/Docker-Ready-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)
![Maven](https://img.shields.io/badge/Maven-Build-red)

This project was created as part of a collaborative work for an Advanced Programming Bootcamp by a team of 6 developers: **Mauricio Jaramillo**, **Jheyson Andrés**, **Hoiver Valencia**, **Juan Arango**, **Alejandro Vasquez**, and **Hover Muñoz**.

## 📋 About the Project

Red Comunitaria is a community network platform built with Spring Boot that allows users to create publications, events, entrepreneurship opportunities, and interact through comments and reactions. The platform supports different user roles including Administrators, Entrepreneurs, and Explorers.

### Key Features

- **User Management**: Registration and authentication with JWT tokens
- **Publications**: Create and manage community posts
- **Events**: Organize and participate in community events  
- **Entrepreneurship**: Share and discover business opportunities
- **Reactions & Comments**: Interactive engagement system
- **Role-based Access**: Different permissions for Admins, Entrepreneurs, and Explorers
- **Geographic Support**: Department and city management for location-based features

## 🛠️ Technologies Used

- **Backend Framework**: Spring Boot 3.3.5
- **Programming Language**: Java 17
- **Database**: MySQL 8.0
- **Security**: Spring Security with JWT Authentication
- **ORM**: Spring Data JPA with Hibernate
- **Build Tool**: Maven
- **Containerization**: Docker & Docker Compose
- **Additional Libraries**:
  - ModelMapper for DTO mapping
  - Lombok for reducing boilerplate code
  - Auth0 Java JWT for token management

## 📁 Project Structure

```
src/main/java/com/talentoTechGrupo3/redComunitaria/
├── comments/          # Comment management system
├── config/            # Security and application configuration
├── publications/      # Publications, events, and entrepreneurship
├── reactions/         # Reaction system for posts and comments
├── users/             # User management and authentication
└── RedComunitariaApplication.java
```

## 🚀 Local Deployment

### Prerequisites

- Java 17 or higher
- Maven 3.6+
- Docker and Docker Compose
- Git

### Option 1: Using Docker Compose (Recommended)

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd RedComunitaria_Bootcamp
   ```

2. **Build and run with Docker Compose**
   ```bash
   docker-compose up --build
   ```

3. **Access the application**
   - API Base URL: `http://localhost:8080`
   - MySQL Database: `localhost:3307`

### Option 2: Manual Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd RedComunitaria_Bootcamp
   ```

2. **Set up MySQL Database**
   ```sql
   CREATE DATABASE `red-comunitaria`;
   CREATE USER 'duas'@'localhost' IDENTIFIED BY 'Rubio_456123';
   GRANT ALL PRIVILEGES ON `red-comunitaria`.* TO 'duas'@'localhost';
   ```

3. **Configure Environment Variables**
   ```bash
   export MYSQL_HOST=localhost
   export MYSQL_PORT=3306
   export MYSQL_DATABASE=red-comunitaria
   export MYSQL_USER=duas
   export MYSQL_PASSWORD=Rubio_456123
   ```

4. **Build and run the application**
   ```bash
   ./mvnw clean package
   java -jar target/redComunitaria-0.0.1-SNAPSHOT.jar
   ```

## 🔧 Configuration

### Database Configuration

The application uses environment variables for database configuration:

- `MYSQL_HOST`: Database host (default: mysql_database for Docker)
- `MYSQL_PORT`: Database port (default: 3306)
- `MYSQL_DATABASE`: Database name (red-comunitaria)
- `MYSQL_USER`: Database username
- `MYSQL_PASSWORD`: Database password

### Application Properties

Key configuration in `application.properties`:
- JPA/Hibernate auto-DDL update enabled
- SQL logging enabled for development
- Server accessible from all interfaces (0.0.0.0)

## 📚 API Endpoints

The application provides REST APIs for:

- **Authentication**: `/auth/*` - User login and registration
- **Users**: `/admin/*`, `/entrepreneur/*`, `/explorer/*` - User management
- **Publications**: `/publications/*` - Content management
- **Events**: `/events/*` - Event management
- **Entrepreneurship**: `/entrepreneurship/*` - Business opportunities
- **Comments**: `/comments/*` - Comment system
- **Reactions**: `/reactions/*` - Like/reaction system
- **Geographic**: `/departments/*`, `/cities/*` - Location management

## 🧪 Testing

Run the test suite:
```bash
./mvnw test
```

## 🤝 Contributing

This project was developed as part of an educational bootcamp. The development team consists of:

- **Mauricio Jaramillo**
- **Jheyson Andrés** 
- **Hoiver Valencia**
- **Juan Arango**
- **Alejandro Vasquez**
- **Hover Muñoz**

## 📄 License

This project is part of an educational program and is intended for learning purposes.

---

**Note**: Make sure to update database credentials and JWT secrets before deploying to production environments.