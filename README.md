# 🏥 CareSync - Hospital Management System

<div align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="Spring">
  <img src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
  <img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white" alt="Hibernate">
  <img src="https://img.shields.io/badge/JSP-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="JSP">
  
  <h3>Comprehensive Hospital Management Solution</h3>
  <p>A full-stack web application for streamlined patient management, appointment scheduling, and medical record handling.</p>
</div>

---

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

## 🎯 Overview

**CareSync** is a comprehensive hospital management system designed to digitize and streamline healthcare operations. The system provides an integrated platform for managing patients, scheduling appointments, and maintaining medical records with security and efficiency at its core.

This project demonstrates full-stack development expertise with a clean **MVC architecture**, RESTful API design, and database optimization techniques.

---

## ✨ Features

### 👤 Patient Management
- ✅ Patient registration and profile management
- ✅ Medical history tracking
- ✅ Patient search and filtering
- ✅ Secure data encryption

### 📅 Appointment System
- ✅ Schedule appointments with doctors
- ✅ Real-time availability checking
- ✅ Appointment reminders
- ✅ Reschedule and cancellation options

### 👨‍⚕️ Doctor Management
- ✅ Doctor profiles and specialization
- ✅ Schedule management
- ✅ Availability tracking
- ✅ Performance metrics

### 📊 Medical Records
- ✅ Digital patient records
- ✅ Prescription management
- ✅ Lab reports storage
- ✅ Medical history reports

### 🔐 Security & Access Control
- ✅ Role-based access control (RBAC)
- ✅ Secure authentication
- ✅ Data encryption
- ✅ Audit trails

### 📈 Dashboard & Reports
- ✅ Administrative dashboard
- ✅ Patient analytics
- ✅ Revenue reports
- ✅ Performance metrics

---

## 🛠️ Technology Stack

| Category | Technology |
|----------|-----------|
| **Backend Language** | Java (JDK 11+) |
| **Framework** | Spring Framework, Spring MVC |
| **ORM** | Hibernate |
| **Web Server** | Apache Tomcat |
| **Database** | MySQL 8.0+ |
| **Frontend** | JSP, HTML5, CSS3, JavaScript |
| **Build Tool** | Maven |
| **IDE** | Eclipse / IntelliJ IDEA |
| **Version Control** | Git & GitHub |

---

## 📁 Project Structure

```
caresync/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/caresync/
│   │   │       ├── models/           # Entity classes
│   │   │       ├── controllers/      # Spring Controllers
│   │   │       ├── services/         # Business logic
│   │   │       ├── repositories/     # Data access layer
│   │   │       ├── utils/            # Utility classes
│   │   │       └── config/           # Configuration classes
│   │   ├── resources/
│   │   │   ├── application.properties
│   │   │   └── hibernate.cfg.xml
│   │   └── webapp/
│   │       ├── WEB-INF/
│   │       │   └── views/           # JSP files
│   │       ├── css/                 # Stylesheets
│   │       ├── js/                  # JavaScript files
│   │       └── images/              # Image assets
│   └── test/
│       └── java/                    # Unit tests
├── pom.xml                          # Maven configuration
└── README.md                        # This file
```

---

## 🚀 Installation

### Prerequisites
- **JDK 11 or higher** installed
- **MySQL Server** (8.0+) running
- **Apache Tomcat** (9.0+)
- **Maven** (3.6+)
- **Git**

### Step 1: Clone the Repository
```bash
git clone https://github.com/Dev-ma-w/caresync.git
cd caresync
```

### Step 2: Create Database
```sql
CREATE DATABASE caresync;
USE caresync;

-- Import the provided SQL schema
SOURCE src/main/resources/database/caresync_schema.sql;
SOURCE src/main/resources/database/caresync_data.sql;
```

### Step 3: Configure Database Connection
Update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/caresync
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
hibernate.show_sql=false
hibernate.format_sql=true
```

### Step 4: Build the Project
```bash
mvn clean install
```

### Step 5: Deploy on Tomcat
```bash
mvn tomcat7:deploy
# or copy the WAR file to Tomcat's webapps directory
cp target/caresync.war $CATALINA_HOME/webapps/
```

---

## ▶️ Running the Application

### Start Apache Tomcat
```bash
# Linux/Mac
$CATALINA_HOME/bin/startup.sh

# Windows
$CATALINA_HOME\bin\startup.bat
```

### Access the Application
```
http://localhost:8080/caresync
```

### Default Login Credentials
| Role | Username | Password |
|------|----------|----------|
| Admin | admin | admin@123 |
| Doctor | doctor | doctor@123 |
| Patient | patient | patient@123 |

---

## 🔌 API Endpoints

### Patient Management
```
GET    /api/patients              - Get all patients
GET    /api/patients/{id}         - Get patient by ID
POST   /api/patients              - Create new patient
PUT    /api/patients/{id}         - Update patient
DELETE /api/patients/{id}         - Delete patient
GET    /api/patients/search       - Search patients
```

### Appointment Management
```
GET    /api/appointments          - Get all appointments
GET    /api/appointments/{id}     - Get appointment by ID
POST   /api/appointments          - Book appointment
PUT    /api/appointments/{id}     - Update appointment
DELETE /api/appointments/{id}     - Cancel appointment
GET    /api/appointments/doctor/{id} - Doctor's appointments
```

### Doctor Management
```
GET    /api/doctors               - Get all doctors
GET    /api/doctors/{id}          - Get doctor by ID
GET    /api/doctors/specialization/{spec} - Doctors by specialization
POST   /api/doctors               - Add doctor (admin)
PUT    /api/doctors/{id}          - Update doctor (admin)
```

---

## 📸 Screenshots

### Login Dashboard
![Dashboard](docs/screenshots/dashboard.png)

### Patient Management
![Patient Management](docs/screenshots/patient-management.png)

### Appointment Booking
![Appointment Booking](docs/screenshots/appointment-booking.png)

### Admin Dashboard
![Admin Dashboard](docs/screenshots/admin-dashboard.png)

---

## 🔄 Database Schema

### Entity Relationship Diagram
```
Patients (1) ----< (M) Appointments
   |
   +----< (M) Medical_Records
   
Doctors (1) ----< (M) Appointments
   |
   +----< (M) Schedules

Users (1) ----< (M) Audit_Logs
```

---

## 🎯 Future Enhancements

- [ ] Mobile app for iOS and Android
- [ ] Real-time notification system with WebSockets
- [ ] Video consultation feature
- [ ] AI-based diagnosis assistance
- [ ] Integration with electronic health records (EHR)
- [ ] Insurance billing module
- [ ] Telemedicine capabilities
- [ ] Advanced reporting and analytics
- [ ] Multi-language support
- [ ] Mobile-first responsive design optimization

---

## 📝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the **MIT License**.

---

## 🤝 Support

For support, email [manojdev3003@gmail.com](mailto:manojdev3003@gmail.com) or reach out on [LinkedIn](https://www.linkedin.com/in/dev-manoj-s-176027258/).

---

## 👨‍💻 Author

**Dev Manoj S**
- 🌐 Portfolio: [devmanoj.vercel.app](https://devmanoj.vercel.app)
- 💼 LinkedIn: [@dev-manoj-s-176027258](https://www.linkedin.com/in/dev-manoj-s-176027258/)
- 📧 Email: [manojdev3003@gmail.com](mailto:manojdev3003@gmail.com)
- 🔗 GitHub: [@Dev-ma-w](https://github.com/Dev-ma-w)

---

<div align="center">

**⭐ If you found this helpful, please consider giving it a star!**

Made with ❤️ by Dev Manoj S

</div>
