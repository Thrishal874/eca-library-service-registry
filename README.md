# ECA Library - Service Registry (Netflix Eureka)

Centralized service registration and discovery server for the **Educational Campus Academy (ECA) Library Management System**.

---

## 📌 Student & Project Mandatory Information
- **Student Name:** Thrishal Weerasooriya
- **Student Number:** [Your Student ID / e.g. GDSE-XX-XXXX]
- **Slack Handle:** [Your Slack Handle / e.g. @thrishal] *(Optional)*
- **GCP Project ID:** eca-library-management-system *(Replace with your exact GCP Project ID)*

---

## 📖 Project Description
The **Service Registry** component provides automated service registration, heartbeat health tracking, and dynamic service discovery using **Spring Cloud Netflix Eureka Server**.

### Key Features
- Dynamic registration for all microservices (`CUSTOMER-SERVICE`, `BOOK-SERVICE`, `RECORD-SERVICE`, `API-GATEWAY`).
- Real-time web dashboard displaying instance metadata, status, IP addresses, and lease renewal timings.
- Eliminates hardcoded service URLs and supports dynamic load balancing (`lb://`).
- Critical second service to boot in the startup sequence after the Config Server.

---

## 🛠️ Technology Stack
- **Language:** Java 25 / 17
- **Framework:** Spring Boot 3.x
- **Platform Technology:** Spring Cloud Netflix Eureka Server (`spring-cloud-starter-netflix-eureka-server`)
- **Config Client:** Spring Cloud Config Client (`spring-cloud-starter-config`)
- **Build Tool:** Apache Maven
- **Default Port:** `9001`

---

## ⚙️ Configuration Details
- **Port:** `9001`
- **Application Name:** `service-registry`
- **Config Server URL:** `http://localhost:9000`
- **Eureka Dashboard URL:** `http://localhost:9001`

---

## 🚀 Setup & Getting Started Instructions

### Prerequisites
- JDK 17 or JDK 25 installed
- Apache Maven 3.8+ installed
- Config Server running on port `9000`

### Build the Artifact
```bash
mvn clean package -DskipTests
```

### Run Locally (Maven)
```bash
mvn spring-boot:run
```

### Run Executable JAR
```bash
java -jar target/service-registry-1.0.0.jar
```

### Run with PM2 (GCP VM Deployment)
```bash
pm2 start target/service-registry-1.0.0.jar --name "service-registry"
```

### Verification
Open the Eureka Web Dashboard in your browser:
[http://localhost:9001](http://localhost:9001)

You should see registered instances listed under "Instances currently registered with Eureka".
