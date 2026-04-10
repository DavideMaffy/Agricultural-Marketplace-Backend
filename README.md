# 🌾 Agricultural Marketplace Backend

Backend application for an agricultural marketplace developed as a university project.
Built with **Java** and **Spring Boot**, the system manages users, products, and orders using **Hibernate/JPA** for data persistence.

---

## 🚀 Tech Stack

* Java
* Spring Boot
* Hibernate / JPA
* Maven
* MySQL

---

## 📌 Features

* User management
* Product management
* Order handling
* RESTful API architecture
* Database persistence with Hibernate

---

## 🏗️ Architecture

The project follows a **layered architecture**:

* **Controller** → Handles HTTP requests
* **Service** → Contains business logic
* **Repository** → Manages database operations
* **Entity** → Defines data models

---

## 🧪 Testing the Application

This application does **not include a frontend interface**.

To facilitate testing, sample data (users and products) are automatically initialized at startup inside the `FilieraApplication` class.

This allows immediate interaction with the system without requiring manual database setup.

The application can be tested using API clients such as:

* Postman
* cURL

---

## 📡 API Usage

All functionalities are exposed through RESTful endpoints.

You can:

* Retrieve existing data
* Create new resources
* Update entities
* Delete records

Detailed endpoint descriptions are provided below.

---

## ⚙️ Prerequisites

* Java 21+
* Maven
* MySQL

---

## 🔧 Configuration

Make sure your database is running and correctly configured in the `application.properties` file before starting the application.

---

## ▶️ Run the Application

You can run the application either from the command line or directly from your IDE.

### 🔹 Run via Terminal

Make sure you are in the root directory (where `pom.xml` is located), then run:

```bash
mvn spring-boot:run
```

The application will start on:

```
http://localhost:8080
```

---

### 🔹 Run via IDE

1. Open the project
2. Locate the main class: `FilieraApplication`
3. Run the `main` method

Once running, you can interact with the API using tools like Postman.

---

## 📡 API Endpoints

The application exposes RESTful APIs organized by user roles.

---

### 🔐 Authentication

Base path: `/auth`

* **POST /auth/registerUser** → Register a new user
* **POST /auth/registerSeller** → Register a new seller

---

### 🌍 Public

Base path: `/public`

* **GET /public/products** → Retrieve approved products
* **GET /public/bundles** → Retrieve bundles
* **GET /public/map** → Retrieve vendor locations
* **GET /public/map/{vendorId}** → Retrieve vendor address
* **GET /public/eventi** → Retrieve events
* **POST /public/{prodottoId}/condividi** → Share product

---

### 🛒 Buyer (Acquirente)

Base path: `/acquirente`

**Cart**

* POST `/add` → Add product (params: product, quantity)
* POST `/remove` → Remove product
* POST `/clear` → Clear cart
* GET `/carrello` → Get cart

**Orders**

* POST `/buy` → Purchase cart

**Products**

* GET `/products` → Retrieve products

**Events**

* POST `/prenota/{eventId}` → Book event
* DELETE `/rimuovi/{eventId}` → Cancel booking
* GET `/eventiPrenotati` → Get booked events

---

### 🛍️ Seller (Venditore)

Base path: `/venditore`

**Products**

* GET `/products` → Retrieve all products
* GET `/product/{id}` → Get product by ID
* GET `/approved-products` → Get approved products
* POST `/create-product` → Create product
* PUT `/update-product/{productId}` → Update product
* DELETE `/delete-product/{productId}` → Delete product

**Bundles**

* POST `/create-bundle` → Create bundle
* DELETE `/delete-bundle/{bundleId}` → Delete bundle

**Invitations**

* GET `/evento/visualizzaInviti` → View invitations
* PATCH `/evento/{invitoId}` → Respond to invitation

---

### 🧑‍🌾 Curator (Curatore)

Base path: `/curatore`

* GET `/products` → Retrieve products
* PUT `/approve-product` → Approve product
* PUT `/reject-product` → Reject product
* GET `/products/by-state` → Filter by state
* GET `/products/pending-approval` → Pending products

---

### 🎉 Event Organizer (Animatore)

Base path: `/api/animatore/eventi`

* POST `/create-event` → Create event
* POST `/{eventId}/invite/{sellerId}` → Invite seller
* DELETE `/{eventId}` → Delete event

---

### 🛠️ Admin

Base path: `/admin`

* POST `/approve/{userId}` → Approve user
* GET `/listaDaApprovare` → Users pending approval

---

## 🎓 Purpose

This project was developed as part of my Computer Science studies to apply:

* Backend development
* REST API design
* Database management
* Object-oriented programming

---

## 🔮 Future Improvements

* Frontend integration
* Docker support
* Unit and integration testing

---

## 👤 Authors

* Davide Mafalda
* Lorenzo Di Michele
* Mattia Scattu

