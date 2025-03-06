# Reembolso System - Fullstack Setup

## 🛠 Overview
This repository provides a **Dockerized setup** for running both the **backend** (Rails API) and **frontend** (Vue.js) as separate services within a unified environment. The backend handles authentication and reimbursement management, while the frontend provides an interactive user interface for managing reimbursements.

---

## 🚀 Prerequisites
Ensure you have **Docker** and **Docker Compose** installed:
- [Docker Installation](https://docs.docker.com/get-docker/)
- [Docker Compose Installation](https://docs.docker.com/compose/install/)

---

## 📌 Clone the Repositories
Clone both the **API** and **frontend** repositories:

```bash
git clone https://github.com/tiagorahal/reembolso_api
cd reembolso_api
```

```bash
git clone https://github.com/tiagorahal/reembolso
cd reembolso
```

---

## 🐳 **Running the Fullstack Application with Docker**
### 1️⃣ Navigate to the `reembolso_api` directory
```bash
cd reembolso_api
```

### 2️⃣ Build and Run the Containers
```bash
docker compose up --build -d
```
This will:
- Build the necessary Docker images
- Start the **PostgreSQL** database
- Start the **Rails API**
- Start the **Vue.js frontend**

👉 **Verify running containers:**
```bash
docker compose ps
```

---

## 🗃️ **Database Setup**
Run the following command to create and migrate the database:
```bash
docker compose exec web rails db:setup
```
If you need to run migrations separately:
```bash
docker compose exec web rails db:migrate
```

---

## 🌐 **Accessing the Application**

- **Backend (Rails API):**
  - 📟 `http://localhost:3000`

- **Frontend (Vue.js):**
  - 🌍 `http://localhost:5173`


---

## 🔄 **Development Workflow**
### Restarting Services
To restart the services after changes:
```bash
docker compose restart
```

### Stopping the Application
```bash
docker compose down
```

### Viewing Logs
To monitor logs for debugging:
```bash
docker compose logs -f
```

---

## 🔒 **Authentication & API Usage**
- The backend uses **token-based authentication**.
- Authenticated requests must include a valid token.
- Tokens are stored in cookies for secure access.

---

## 🎯 **Key Features**
✅ **Fully Dockerized** for easy deployment
✅ **Vue.js + TypeScript** frontend
✅ **Rails API** backend with PostgreSQL
✅ **User Authentication & Authorization**
✅ **Responsive UI with Bootstrap**
✅ **Secure API with token-based authentication**


---

## 🚀 **Further Development**
- CI/CD Pipeline integration
- Unit & Integration Testing
- Enhanced error handling & logging

---

## 👨‍💻 **Contributing**
1. Fork the repository
2. Create a new branch: `git checkout -b feature-branch`
3. Commit your changes: `git commit -m 'Add feature XYZ'`
4. Push to the branch: `git push origin feature-branch`
5. Open a Pull Request
