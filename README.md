#  Synapse Fitness a Fitness app using Springboot Microservices 

This repository contains a distributed microservices system designed with modularity, scalability, and high availability in mind.  
The system integrates user management, activity tracking, AI processing, and external LLM services while leveraging a centralized authentication server, message queue, service discovery, and configuration management.

---

## 🚀 Core Components

### 1. **API Gateway**

### 2. **Auth Server (Keycloak)**

## 🧩 Microservices

### **USER Service**
- Stores and manages user profile information  
- Backend database: **MySQL**  
- Registers self with the Eureka Service Registry  
- Communicates asynchronously via RabbitMQ where needed

---

### **ACTIVITY Service**
- Responsible for user activity logging  
- Backend database: **MongoDB**  
- Publishes events to the message queue (RabbitMQ) for asynchronous processing

---

### **AI Service**
- Processes activity or user data  
- Performs AI-driven tasks (summaries, insights, predictions, etc.)  
- Backend database: **MongoDB**  
- Consumes messages from RabbitMQ  
- Integrates with **Google Gemini API** for advanced AI inference

---

## 🔗 External Integrations

### **Google Gemini Server**
- Used by AI Service for text generation, recommendations, and other intelligent tasks

---

## 📡 Infrastructure Services

### **RabbitMQ**
Message broker used for:
- Asynchronous communication  
- Event-driven architecture  
- Offloading heavy AI tasks from primary services  

### **Config Server**
- Centralized configuration management for all microservices  
- Hot-reload support (Spring Cloud Config)

### **Eureka Server**
- Service discovery and health monitoring  
- Eliminates the need for hard-coded service URLs

---

## How to Run 

1. Start infrastructure:
   - RabbitMQ  
   - Config Server  
   - Eureka Server  
   - Keycloak  

2. Start microservices:
   - USER Service  
   - ACTIVITY Service  
   - AI Service  

3. Start API Gateway.

4. Access system via:
   - http://localhost:8080/

