<div align="center">

# 📚 BookSocial

### A full-stack social platform for book lovers

BookSocial combines a social reading community, book catalog, e-commerce features and administration tools in a multi-application architecture.

<br>

![Java](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)

</div>

---

## 📖 About BookSocial

**BookSocial** is a full-stack web application designed to create a social experience around books and reading.

The platform allows users to explore books and authors, interact with the community, participate in events, manage their profiles and place orders.

The project also includes a dedicated administration panel for managing the platform's content and business data.

From a technical perspective, BookSocial follows a multi-application architecture composed of a **Spring Boot REST API**, a public **Spring Boot + Thymeleaf frontend**, a **Vue.js administration panel**, and a **MySQL database**.

The entire environment can be deployed locally using **Docker Compose**.

---

## ✨ Main Features

### 👤 Users & Authentication

- User registration and login
- User profiles
- Authentication and authorization
- User management
- Premium subscriptions

### 📚 Book Platform

- Book/work catalog
- Authors
- Publishers
- Editions
- Volumes
- Chapters
- Detailed book information
- Book tracking

### 💬 Community

- User comments
- Reactions
- Community interactions
- User profiles
- Reading-related activity

### 🎟️ Events

- Event listing
- Event management
- Community-oriented events

### 🛒 E-commerce

- Product inventory
- Shopping cart
- Orders
- Order lines
- Order tracking
- User order history

### ⚙️ Administration

Dedicated **Vue.js administration panel** for managing:

- Books
- Authors
- Publishers
- Editions
- Volumes
- Chapters
- Inventory
- Orders
- Users
- Comments
- Events

---

## 🏗️ Architecture

BookSocial is divided into several independent applications that communicate with each other.

```text
                         ┌─────────────────────┐
                         │        USER         │
                         └──────────┬──────────┘
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
                    ▼                               ▼
          ┌──────────────────┐            ┌──────────────────┐
          │      NGINX       │            │   Vue.js Admin   │
          │    Port 80/443   │            │    Port 8080     │
          └────────┬─────────┘            └────────┬─────────┘
                   │                               │
                   ▼                               │
        ┌─────────────────────┐                    │
        │ Spring + Thymeleaf  │                    │
        │   Public Frontend   │                    │
        └──────────┬──────────┘                    │
                   │                               │
                   └───────────────┬───────────────┘
                                   │
                                   ▼
                       ┌─────────────────────┐
                       │  Spring Boot REST   │
                       │         API         │
                       │      Port 9999      │
                       └──────────┬──────────┘
                                  │
                                  ▼
                       ┌─────────────────────┐
                       │        MySQL        │
                       │      Database       │
                       └─────────────────────┘
```

The backend and database operate inside a private Docker network and are accessed through the frontend applications.

---

## 🛠️ Tech Stack

### Backend

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=flat-square&logo=apachemaven&logoColor=white)

### Frontend

![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat-square&logo=thymeleaf&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=flat-square&logo=vuedotjs&logoColor=4FC08D)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

### Database

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

### Infrastructure & Tools

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)

---

## 📁 Project Structure

```text
booksocial/
│
├── booksocial-backend/
│   └── booksocial-backend/
│       └── Spring Boot REST API
│
├── booksocial-frontend/
│   └── Spring Boot + Thymeleaf public frontend
│
├── booksocial-vue/
│   └── Vue.js administration panel
│
├── data/
│   └── MySQL initialization data
│
├── docs/
│   └── Project documentation
│
├── scripts/
│   └── Utility and data export scripts
│
├── uploads/
│   └── Application uploaded files
│
├── .env.example
├── .dockerignore
├── .gitignore
├── docker-compose.yml
│
└── README.md
```

---

## 🐳 Running with Docker

The easiest way to run the complete application is using Docker Compose.

### 1. Clone the repository

```bash
git clone https://github.com/Jorgegf04/booksocial.git
cd booksocial
```

### 2. Create the environment file

Copy the example environment configuration:

```bash
cp .env.example .env
```

Email credentials are optional for normal testing.

If you want to test email functionality, configure:

```env
MAIL_USERNAME=
MAIL_PASSWORD=
```

### 3. Start the application

```bash
docker compose up -d --build
```

Docker will build and start all required services.

The first startup may take a few minutes while the images and project dependencies are downloaded.

### 4. Check the containers

```bash
docker compose ps
```

### 5. Stop the application

```bash
docker compose down
```

To stop the application and remove the database volume:

```bash
docker compose down -v
```

---

## 🐳 Docker Services

| Service | Container | Access | Purpose |
|---|---|---|---|
| MySQL | `mysql-db` | Internal | Main BookSocial database |
| Backend API | `backend-api` | Internal `9999` | Spring Boot REST API |
| Thymeleaf Frontend | `frontend-thymeleaf` | Through Nginx | Public web application |
| Nginx | `nginx-thymeleaf` | `80 / 443` | Reverse proxy |
| Vue Frontend | `frontend-vue` | `localhost:8080` | Administration panel |

The backend and MySQL database are not directly exposed to the host when running the complete Docker environment.

---

## 🌐 Application URLs

Once the application is running:

| URL | Application |
|---|---|
| `http://localhost` | Public BookSocial application |
| `https://localhost` | Public application using local HTTPS |
| `http://localhost:8080` | Vue administration panel |
| `http://localhost:8080/api/...` | Backend API through the Vue proxy |

---

## 🖥️ Public Application

Main routes available through the public frontend:

| Route | Description |
|---|---|
| `/` | Home |
| `/catalog` | Book catalog |
| `/work/{id}` | Book/work details |
| `/authors` | Authors |
| `/author/{id}` | Author details |
| `/community` | Community |
| `/events` | Events |
| `/cart` | Shopping cart |
| `/orders` | User orders |
| `/user/me` | Current user profile |
| `/user/{id}` | User profile |
| `/subscription/premium` | Premium subscription |
| `/auth/login` | Login |
| `/auth/register` | Registration |
| `/auth/logout` | Logout |

---

## ⚙️ Administration Panel

The Vue.js administration panel is available at:

```text
http://localhost:8080
```

Main routes:

| Route | Resource |
|---|---|
| `/login` | Administrator login |
| `/admin/dashboard` | Dashboard |
| `/admin/obras` | Books / works |
| `/admin/autores` | Authors |
| `/admin/editoriales` | Publishers |
| `/admin/ediciones` | Editions |
| `/admin/tomos` | Tomes |
| `/admin/capitulos` | Chapters |
| `/admin/volumenes` | Volumes |
| `/admin/inventario` | Inventory |
| `/admin/pedidos` | Orders |
| `/admin/usuarios` | Users |
| `/admin/comentarios` | Comments |
| `/admin/eventos` | Events |

---

## 🔌 REST API

The Spring Boot backend exposes a REST API used by the frontend applications.

When running with Docker, the API can be accessed through:

```text
http://localhost:8080/api/...
```

### Main endpoints

| Endpoint | Resource |
|---|---|
| `/api/auth/login` | Authentication |
| `/api/auth/register` | User registration |
| `/api/users` | Users |
| `/api/authors` | Authors |
| `/api/works` | Books / works |
| `/api/editorials` | Publishers |
| `/api/editions` | Editions |
| `/api/tomes` | Tomes |
| `/api/chapters` | Chapters |
| `/api/volumes` | Volumes |
| `/api/products` | Products and inventory |
| `/api/orders` | Orders |
| `/api/order-lines` | Order lines |
| `/api/comments` | Comments |
| `/api/reactions` | Reactions |
| `/api/events` | Events |
| `/api/subscriptions` | Subscriptions |
| `/api/tracking-works` | Book tracking |
| `/api/tracking-orders` | Order tracking |
| `/api/upload` | File uploads |

---

## 💻 Running Without Docker

The applications can also be started individually during development.

### Backend API

```bash
cd booksocial-backend/booksocial-backend
mvn spring-boot:run
```

Available at:

```text
http://localhost:9999
```

### Thymeleaf Frontend

```bash
cd booksocial-frontend
mvn spring-boot:run
```

Available at:

```text
http://localhost:8000
```

### Vue Administration Panel

```bash
cd booksocial-vue
npm install
npm run dev
```

Usually available at:

```text
http://localhost:5173
```

---

## 💾 Database Initialization

If the following SQL dump exists:

```text
data/mysql-init/01-booksocial.sql
```

the MySQL container automatically imports it when the database volume is created for the first time.

To recreate the database from the initialization script:

```bash
docker compose down -v
docker compose up -d --build
```

---

## 📦 Exporting Development Data

A PowerShell utility script is included to prepare development data for another machine.

With the Docker containers running:

```powershell
.\scripts\export-delivery-data.ps1
```

The script generates or updates:

```text
data/mysql-init/01-booksocial.sql
uploads/
```

The SQL dump contains the database data while the `uploads` directory contains files uploaded through the application.

---

## 🔧 Useful Docker Commands

### View all logs

```bash
docker compose logs -f
```

### Backend logs

```bash
docker compose logs -f backend-api
```

### Public frontend logs

```bash
docker compose logs -f frontend-thymeleaf
```

### Vue frontend logs

```bash
docker compose logs -f frontend-vue
```

### MySQL logs

```bash
docker compose logs -f mysql-db
```

### Rebuild only the backend

```bash
docker compose up -d --build backend-api
```

### Rebuild only the Thymeleaf frontend

```bash
docker compose up -d --build frontend-thymeleaf
```

### Rebuild only the Vue frontend

```bash
docker compose up -d --build frontend-vue
```

### Access MySQL from Docker

```bash
docker compose exec mysql-db mysql -uroot -p booksocial
```

---

## 🎯 What This Project Demonstrates

BookSocial was developed as a full-stack project to apply concepts such as:

- REST API design with Spring Boot
- Layered backend architecture
- Relational database modeling
- Authentication and authorization
- Backend/frontend communication
- Server-side rendering with Thymeleaf
- SPA development with Vue.js
- Containerized environments with Docker
- Reverse proxy configuration with Nginx
- Environment-based configuration
- Full-stack application integration

---

## 🔮 Future Improvements

Some improvements that can be incorporated into future versions:

- [ ] Increase automated test coverage
- [ ] Add API documentation with OpenAPI / Swagger
- [ ] Implement CI/CD with GitHub Actions
- [ ] Improve application monitoring and logging
- [ ] Deploy the application to a cloud environment
- [ ] Improve responsive UI/UX
- [ ] Add additional community features

---

## 👨‍💻 Author

**Jorge Guijarro**

Junior Backend Developer focused on **Java, Spring Boot, REST APIs and SQL**.

[![GitHub](https://img.shields.io/badge/GitHub-Jorgegf04-181717?style=for-the-badge&logo=github)](https://github.com/Jorgegf04)

---

<div align="center">

### ⭐ If you find this project interesting, feel free to explore the repository.

Built as part of my journey into professional backend development.

</div>
