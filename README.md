# 🛒 E-Commerce Microservices Architecture  
**Software Architecture and Design – Group Assignment**

---

## 📌 Project Overview
This project demonstrates an **E-commerce Platform** built using the **Microservices Architecture Style**.  
Each core business capability is implemented as an independent microservice, allowing the system to be **scalable, resilient, and easy to maintain**.

The project is developed as part of the **Software Architecture and Design** course at **FIT – Industrial University of Ho Chi Minh City (IUH)**.

---

## 👥 Team Members – Software Architecture Group
- **Nguyễn Trung Nguyên**
- **Nguyễn Trần Gia Sĩ**
- **Nguyễn Văn Minh**
- **Đào Quốc Tuấn**

---

## 🧩 System Architecture Overview
The system is composed of multiple loosely coupled microservices communicating through **REST APIs** and **asynchronous messaging**, with an **API Gateway** acting as a single entry point.

### Key Characteristics
- Independent services and databases  
- Centralized API Gateway  
- Synchronous & asynchronous communication  
- Horizontal scalability and fault isolation  

---

## 🛠️ Microservices List

### 1️⃣ User Service
- Handles user registration, authentication, and profile management  
- Uses **JWT / OAuth** for secure authentication  
- Stores user data in a dedicated database  

### 2️⃣ Product Catalog Service
- Manages products, categories, pricing, and images  
- Supports search and filtering features  
- Optimized for fast querying using NoSQL databases  

### 3️⃣ Order Service
- Manages the full order lifecycle (create → process → complete)  
- Validates orders and tracks order status  
- Communicates with Inventory and Payment services  

### 4️⃣ Inventory Service
- Tracks product stock levels  
- Updates inventory after successful purchases  
- Notifies Order Service when products are out of stock  

### 5️⃣ Payment Service
- Handles payment transactions securely  
- Integrates with third-party payment gateways (e.g., Stripe, PayPal)  

### 6️⃣ Recommendation Service
- Provides personalized product recommendations  
- Uses user behavior and order history  
- Can be extended with machine learning models  

### 7️⃣ Notification Service
- Sends email or SMS notifications  
- Events include order confirmation, payment success, and shipping updates  

### 8️⃣ API Gateway
- Single entry point for web and mobile clients  
- Routes requests to appropriate services  
- Handles authentication, rate limiting, and load balancing  

---

## 🔗 Communication Patterns
- **Synchronous:** REST / gRPC for real-time service-to-service calls  
- **Asynchronous:** Message broker (Kafka / RabbitMQ) for event-based communication  

---

## 🚀 Implementation Approach

### Step 1: Independent Development
Each microservice has:
- Its own codebase  
- Its own database  
- Its own deployment pipeline  

**Example Technology Stack**
- User Service: Node.js + MongoDB  
- Order Service: Java + PostgreSQL  
- Inventory Service: Python + MySQL  
- Payment Service: Python + External Payment APIs  

### Step 2: API Gateway Integration
- Centralized routing and authentication  
- Simplifies client-side interaction  

### Step 3: Scalability & Resilience
- Horizontal scaling for high-traffic services  
- Service discovery (Consul / Eureka)  
- Circuit breakers and fallback mechanisms  

### Step 4: Monitoring & Logging
- Centralized logging using ELK Stack  
- Monitoring with Prometheus & Grafana  
- Alerting for critical system issues  

---

## 🔄 Order Processing Flow
1. User places an order via frontend  
2. Request is routed through the API Gateway  
3. Order Service checks stock with Inventory Service  
4. Payment Service processes the payment  
5. Inventory is updated after successful payment  
6. Notification Service sends confirmation to the user  
7. Recommendation Service updates user preferences  

---

## ✅ Benefits of Microservices Architecture
- **Independent Scaling:** Scale only high-demand services  
- **Fault Isolation:** Failures do not cascade across the system  
- **Technology Flexibility:** Each service uses the best-fit technology  
- **Faster Deployment:** Services can be updated independently  

---

## 📎 Conclusion
This microservices-based e-commerce system is designed to be **modular, scalable, and resilient**, making it suitable for real-world, high-traffic applications while remaining easy to extend and maintain.

---

**Faculty of Information Technology – IUH**  
**Software Architecture and Design**
