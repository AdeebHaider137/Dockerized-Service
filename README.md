# 🚀 Node.js Auth Service (Dockerized)

A lightweight **Node.js service** demonstrating authentication, environment-based configuration, and containerization with **Docker**.
This project is designed as a simple example of how to build, secure, and deploy a service that can run both locally and in the cloud.

---

## ✨ Features

* 🌐 **Public route** (`/`) → returns a **dynamic greeting with server timestamp** (e.g., `"Welcome! Server time is 2025-09-28 14:35:00"`), demonstrating simple runtime logic beyond static text.
* 🔐 **Protected route** (`/secret`) → requires Basic Auth
* ⚙️ **Environment variable configuration** via `.env`
* 🐳 **Dockerized service** for easy deployment
* 📈 Ready for extension with **health checks, CI/CD pipelines, and cloud deployment**

---

## 📦 Prerequisites

* **Node.js** v14 or higher
* **npm** (Node Package Manager)
* **Docker** (optional, for containerized deployment)

---

## ⚙️ Setup & Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/AdeebHaider137/Dockerized-Service.git
   cd Dockerized-Service
   ```
2. Install dependencies:

   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory:

   ```env
   PORT=3000
   SECRET_MESSAGE=Your secret message here
   USERNAME=your_username
   PASSWORD=your_password
   ```

---

## 🚀 Running the Service

### Development (with auto-reload):

```bash
npm run dev
```

### Production:

```bash
npm start
```

### Docker:

Build the image:

```bash
docker build -t node-auth-service .
```

Run the container:

```bash
docker run -p 3000:3000 --env-file .env node-auth-service
```

---

## 🔍 Testing the Routes

* **Public Route**
  Visit: [http://localhost:3000/](http://localhost:3000/)
  Response example:

  ```
  Welcome! Server time is 2025-09-28 14:35:00
  ```

  *(Dynamic greeting demonstrates server logic and live response)*

* **Protected Route**
  Visit: [http://localhost:3000/secret](http://localhost:3000/secret)
  Enter the credentials from your `.env` file.

  * ✅ Correct → shows the secret message
  * ❌ Incorrect → shows an error message

---

## 🛡️ Security Note

* Always update default credentials before deploying.
* For production use, consider hashing passwords, using HTTPS, and adding rate-limiting.

---

## 📌 About

This project was created to demonstrate:

* Building a **minimal secure service** in Node.js
* **Dockerizing** for cloud deployment
* Using **environment configuration** best practices
* Deploying on **EC2 containers** with **secure GitHub Actions CI/CD**
