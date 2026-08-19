# Tomato - Full-Stack Food Delivery Platform

![MERN Stack](https://img.shields.io/badge/Stack-MERN-blue)
![React](https://img.shields.io/badge/Frontend-React.js-61DAFB)
![Node.js](https://img.shields.io/badge/Backend-Node.js-339933)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248)

A complete, end-to-end food delivery web application built with the MERN stack. Tomato features a customer-facing ordering interface, a secure authentication system, real-time order tracking, and a dedicated admin dashboard for restaurant management.

## ✨ Key Features

### 🧑‍💻 For Customers
* **Browse & Search:** Seamlessly browse food categories and menus.
* **Geospatial Searches:** Find the nearest restaurants efficiently (powered by MongoDB `2dsphere` indexing).
* **Cart Management:** Dynamic global state management for cart operations.
* **Secure Checkout:** Real-world payment processing integrated with the Stripe API.

### 👨‍🍳 For Restaurant Admins
* **Inventory Management:** Add, update, and remove menu items dynamically.
* **Real-Time Order Dashboard:** Instantly view new incoming orders via WebSockets.
* **Order Status Updates:** Update food preparation and delivery statuses live.

---

## 🏗️ System Architecture & Technical Highlights

This project was built with enterprise-level design patterns in mind to handle concurrency, security, and scalability:

* **Real-Time Pub/Sub:** Implemented **Socket.io** backed by **Redis Pub/Sub** to ensure real-time order updates can scale horizontally across multiple Node.js server instances.
* **Secure Authentication:** Utilizes **JSON Web Tokens (JWT)** stored securely in HTTP-only cookies to prevent XSS (Cross-Site Scripting) attacks, coupled with anti-CSRF measures.
* **Fault-Tolerant Payments:** Uses **Stripe Webhooks** with idempotency keys to ensure order statuses are securely and accurately updated, even if the client disconnects mid-payment.
* **Database Concurrency:** Leverages MongoDB document-level atomicity (`$inc` operators) to prevent race conditions during high-traffic checkout events (e.g., preventing double-booking of limited inventory).

---

## 🛠️ Technologies Used

* **Frontend:** React.js, React Router, Context API / Redux, CSS Modules / Tailwind
* **Backend:** Node.js, Express.js
* **Database:** MongoDB, Mongoose
* **Caching & Messaging:** Redis
* **Third-Party APIs:** Stripe (Payments), Multer (Image uploads)

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites
* Node.js (v16 or higher)
* MongoDB (Local instance or MongoDB Atlas URI)
* Redis (Local instance)
* A Stripe Developer Account

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Itz-Sudip/Tomato.git](https://github.com/Itz-Sudip/Tomato.git)
   cd QuiZone-project
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or yarn / pnpm install
   ```

3. **Run the development server:**
   ```bash
   npm run dev
   ```
   The app will be available at `http://localhost:3000` (or the port specified by Vite).

4. **Build for production:**
   ```bash
   npm run build
   ```
## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 
Feel free to check the [issues page](https://github.com/Itz-Sudip/Tomato/issues) if you want to contribute.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
