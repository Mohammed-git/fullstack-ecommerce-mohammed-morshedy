# Full-Stack E-Commerce Platform (ShopShere)

A complete Full-Stack E-Commerce Platform developed as the **Capstone Project** for the **Digital Egypt Cubs Initiative (DECI)**.

The project allows users to browse products, search, filter, add items to the shopping cart, place orders, while providing an Admin Dashboard to manage products.

---

# Features

## Authentication

- User Registration
- User Login
- JWT Authentication
- Protected Routes
- Admin & Customer Roles
- Welcome Email

## Product Management

- Create Product
- Update Product
- Delete Product
- Product Search
- Product Filter
- Product Sorting
- Pagination
- Product Image Upload

## Shopping

- Shopping Cart
- Checkout
- Order Management

## Additional Features

- Product Reviews (MongoDB)
- Activity Logs (MongoDB)
- Store Statistics API
- Database Seed

## Testing

- Jest
- Supertest
- Vitest
- React Testing Library
- Mock Service Worker (MSW)

## DevOps

- Docker
- Docker Compose

---

# Technologies Used

## Frontend

- React
- React Router
- React Query
- Axios
- Vite

## Backend

- Node.js
- Express.js
- Prisma ORM
- PostgreSQL
- MongoDB
- JWT
- Multer
- Nodemailer
- Bcrypt

## Testing

- Jest
- Supertest
- Vitest
- React Testing Library
- MSW

---

# Project Structure

```text
fullstack-ecommerce-mohammed-morshedy
│
├── frontend
│
├── backend
│
├── docker-compose.yml
│
├── README.md
│
└── README.txt
```

---

# Project URLs

Frontend

http://localhost:5173

Backend API

http://localhost:5000/api

Health Check

http://localhost:5000/

---

# Requirements

Before running the project, make sure you have installed:

- Git
- Docker Desktop

Docker Desktop must be running before starting the project.

---

# Getting Started

## Step 1 - Clone the Repository

Open Terminal (or CMD) and run:

```bash
git clone https://github.com/Mohammed-git/fullstack-ecommerce-mohammed-morshedy.git
```

---

## Step 2 - Open the Project Folder

```bash
cd fullstack-ecommerce-mohammed-morshedy
```

---

## Step 3 - Configure Environment Variables

Inside the backend folder:

1. Copy the file

```
.env.example
```

2. Rename the copied file to

```
.env
```

3. Open the new `.env` file.

4. Replace the placeholder values with your own configuration.

Example:

```env
PORT=5000

DATABASE_URL=postgresql://postgres:postgres@postgres:5432/ecommerce?schema=public

MONGO_URI=mongodb://mongodb:27017/ecommerce

JWT_SECRET=your-secret-key

EMAIL_USER=your-email@example.com

EMAIL_PASS=your-email-password
```

> **Note**
>
> EMAIL_USER and EMAIL_PASS are only required if you want Welcome Emails to be sent.
>
> Placeholder values in `.env.example` are provided for reference only.

---

# Run the Project

From the project root run:

```bash
docker compose up --build
```

The first build may take a few minutes.

Docker will automatically:

- Build Frontend
- Build Backend
- Start PostgreSQL
- Start MongoDB
- Seed the Database

When the process finishes you can open:

Frontend

http://localhost:5173

---

# Seed Data

The database is automatically populated with sample data including:

- Admin Account
- Customer Account
- Sample Products

No manual database setup is required.

---

# Test Accounts

## Admin Account

Email

```
mohamed@test.com
```

Password

```
123456
```

---

## Customer Account

Email

```
ahmed@test.com
```

Password

```
123456
```

---

# Running Tests

## Backend Tests

Open a new terminal.

```bash
cd backend
```

Install dependencies.

```bash
npm install
```

```bash
# Generate Prisma Client (!!Very Important & Required!!)
npx prisma generate
```

Run tests.

```bash
npm test
```
```bash
## ⚠️ Important

If this is your **first time cloning** the repository, you **must generate the Prisma Client** before starting the backend or running the backend tests.

```bash
npx prisma generate
```

> **Note:**  
> The Prisma Client is generated locally and is **not included** in this repository. The generated files (`backend/src/generated/prisma`) are ignored by Git, so this command only needs to be run after a fresh clone or whenever the Prisma schema changes.
```

---

## Frontend Tests

Open another terminal.

```bash
cd frontend
```

Install dependencies.

```bash
npm install
```

Run tests.

```bash
npm test
```

---

# Running Without Docker

## Backend

```bash
cd backend

npm install

# Create a .env file from .env.example
# and update the required environment variables

# Generate Prisma Client (Required)
npx prisma generate

# Apply database migrations
npx prisma migrate deploy

# Seed the database (Creates demo accounts)
npx prisma db seed

# Start the backend
npm run dev
```

---

## Frontend

```bash
cd frontend

npm install

npm run dev
```

---

# Databases

This project uses two databases.

## PostgreSQL

Stores:

- Users
- Products
- Orders
- Cart

## MongoDB

Stores:

- Product Reviews
- Activity Logs

---

# Docker

The project contains:

- Backend Dockerfile
- Frontend Dockerfile
- docker-compose.yml

Everything can be started using one command:

```bash
docker compose up --build
```

---
![UptimeRobot Monitoring](uptimerobot-dashboard.png)

# Important Notes

- The project is designed to run using Docker Compose.
- Uploaded images are stored inside `backend/uploads`.
- The database is automatically seeded on first startup.
- Docker Desktop must be running before executing Docker commands.
- Never commit your real `.env` file.
- Use `.env.example` as the environment template.

---
# Production Logging

The backend uses Winston for structured logging.

Production logs can be viewed from:

Vercel Dashboard → Backend Project → Logs / Runtime Logs

The logs include:
- Request entries with timestamp and severity level.
- Error entries with timestamp and severity level.



---
# ShopSphere Enterprise Production and Cloud Modernization

## Digital Egypt Cubs Initiative — Level 5

### Final Project Submission Package

---

## Project Information

| Item | Details |
|---|---|
| **Student ID** | `30810200200418` |
| **Project** | ShopSphere Enterprise Production and Cloud Modernization |
| **Repository** | [GitHub Repository](https://github.com/Mohammed-git/fullstack-ecommerce-mohammed-morshedy) |
| **Main Application** | [Production Application](https://fullstack-ecommerce-mohammed-morshe.vercel.app/) |
| **Review Service** | [Review Microservice](https://mohammed-morshedy-shop-sphere-revie.vercel.app/) |
| **Analytics Function** | [Serverless Analytics](https://mohammed-morshedy-shop-sphere-revie.vercel.app/api/analytics) |

> This document consolidates the ShopSphere project deliverables and supporting evidence for final submission.

---

# Task 1 — Production Deployment

## Production Deployment

The ShopSphere frontend and backend were deployed to **Vercel** and connected to a production **PostgreSQL database hosted on Supabase**.

## Security

The deployed backend uses the following security protections:

- **HTTPS**
- **CORS**
- **Helmet**
- **Rate Limiting**

## Production Database

- **Database:** PostgreSQL
- **Provider:** Supabase
- **Environment:** Production

The production application successfully connects to the Supabase PostgreSQL database and retrieves application data.

## Health Check

The backend provides a production health-check endpoint:

`/health`

The endpoint is used to verify backend availability and is monitored through UptimeRobot.

## Testing

Backend tests completed successfully:

- **Test Suites:** 2 passed
- **Tests:** 8 passed
- **Result:** `8/8 tests passed`

## Monitoring

Production availability is monitored using **UptimeRobot**.

The monitoring configuration checks the production health endpoint and provides uptime and availability status.

---

# Task 2 — Cloud Preparation

## 2.1 Architecture Diagram

The production architecture consists of:

- User / Web Browser
- Vercel Frontend
- Vercel Backend / Serverless Functions
- Supabase PostgreSQL Database
- HTTPS/TLS communication between components

The architecture diagram represents the production deployment and the traffic flow between the major system components.

**Architecture Diagram File:**

`EYOUTH-30810200200418-ShopSphere.png`

## 2.2 Cloud Service Classification

The production cloud services are classified as follows:

| Service | Provider | Service Model |
|---|---|---|
| Frontend Hosting | Vercel | **PaaS** |
| Backend / Serverless Hosting | Vercel | **PaaS** |
| Production Database | Supabase PostgreSQL | **PaaS** |

The reasons for each classification are documented in:

`cloud-classification.md`

## 2.3 Kubernetes Multi-Cloud Simulation

The project includes a Kubernetes-based multi-cloud simulation defined in:

`k8s-simulation.yaml`

The simulation contains two isolated namespaces:

### AWS Simulation

Namespace:

`aws-simulation`

Resources:

- Frontend Pod
- Backend Pod
- Frontend Service
- Backend Service

### GCP Simulation

Namespace:

`gcp-simulation`

Resources:

- Frontend Pod
- Backend Pod
- Frontend Service
- Backend Service

The pods were verified as **Running** and **Ready**, and the backend services were tested using `kubectl port-forward`.

---

# Task 3 — Application Modernization

## 3.1 Review Service Extraction

The Reviews functionality was extracted from the main monolithic backend and converted into an independently deployed **Node.js / Express microservice**.

The Review Service provides dedicated review endpoints, including:

- `GET /api/reviews`
- `POST /api/reviews`

The service is deployed independently and has its own production URL.

**Review Microservice:**

[https://mohammed-morshedy-shop-sphere-revie.vercel.app/](https://mohammed-morshedy-shop-sphere-revie.vercel.app/)

## 3.2 REST Communication

The main ShopSphere backend communicates with the Review Microservice through a **REST API**.

The REST integration is implemented through:

`backend/src/routes/review.routes.js`

The main application forwards review-related requests to the independently deployed Review Service.

## 3.3 Serverless Integration

A Vercel Serverless Function was implemented to handle background analytics and metrics processing.

**Serverless Function:**

`api/analytics.js`

**Production Endpoint:**

[Serverless Analytics Endpoint](https://mohammed-morshedy-shop-sphere-revie.vercel.app/api/analytics)

The function executes independently from the main Express application and is deployed through Vercel Serverless Functions.

## 3.4 Architecture Decision Record

The project's Architecture Decision Record is documented in:

`ADR.md`

The ADR documents two major architectural decisions:

1. Extracting the Reviews functionality into an independent microservice.
2. Using a Serverless Function for background analytics and metrics processing.

---

# Task 4 — Production Operations

## 4.1 CI/CD Pipeline and Secrets

A CI/CD pipeline was implemented using **GitHub Actions**.

The pipeline performs the following operations:

1. Installs backend dependencies.
2. Builds the backend.
3. Installs frontend dependencies.
4. Builds the frontend.
5. Deploys the backend to Vercel production.
6. Deploys the frontend to Vercel production.

Production deployment occurs when changes reach the `main` branch.

### Pipeline Security

Deployment credentials are stored securely using **GitHub Actions Secrets**.

No credentials are hard-coded in the workflow file or exposed in pipeline logs.

### Branch Protection

The `main` branch is protected and requires the **ShopSphere CI/CD Pipeline** check to pass before a pull request can be merged.

---

## 4.2 Structured Logging

The backend uses **Winston** for structured logging.

Log entries are generated in **JSON format** and include:

- Timestamp
- Severity level
- Request information
- Error information

### Request Logging

Incoming requests are logged by backend middleware with information such as:

- HTTP method
- Request URL
- Status information
- Timestamp
- Severity level

### Error Logging

Backend errors are captured by the Express error-handling middleware and logged with:

- Error message
- Stack trace
- Request URL
- Timestamp
- Severity level

### Production Log Location

Production logs can be viewed through the deployed backend's **Vercel runtime/deployment logs**.

---

# 4.3 Rollback Plan

The rollback procedure is documented in:

`Rollback-Plan.md`

The rollback plan covers:

1. Detecting a failed production release using production monitoring.
2. Identifying issues such as health-check failures, error spikes, or latency degradation.
3. Reverting production to the previous stable version.
4. Verifying that the restored version is healthy after rollback.

The rollback procedure is designed to restore the previous working release as quickly as possible.

---

# 4.4 Project Sharing

The following project resources are publicly accessible:

### Main Application

[https://fullstack-ecommerce-mohammed-morshe.vercel.app/](https://fullstack-ecommerce-mohammed-morshe.vercel.app/)

### Review Microservice

[https://mohammed-morshedy-shop-sphere-revie.vercel.app/](https://mohammed-morshedy-shop-sphere-revie.vercel.app/)

### GitHub Repository

[https://github.com/Mohammed-git/fullstack-ecommerce-mohammed-morshedy](https://github.com/Mohammed-git/fullstack-ecommerce-mohammed-morshedy)

---

# Final Submission Checklist

- [x] Project naming convention followed.
- [x] Production application deployed and publicly accessible.
- [x] Review Microservice deployed and publicly accessible.
- [x] GitHub repository publicly accessible.
- [x] Production monitoring configured.
- [x] CI/CD pipeline implemented using GitHub Actions.
- [x] CI/CD pipeline successfully completed.
- [x] `main` branch protected with required CI/CD checks.
- [x] Structured logging implemented.
- [x] Production log location documented.
- [x] Rollback plan documented.
- [x] Architecture diagram included.
- [x] Cloud service classification documented.
- [x] Kubernetes multi-cloud simulation included.
- [x] Architecture Decision Record included.
- [x] No secret values are included in the submission document.

---

## Project Status

**ShopSphere Enterprise Production and Cloud Modernization — Complete**

All four project tasks have been implemented and the required deliverables have been prepared for final submission.

# License

This project was developed for educational purposes as part of the **Digital Egypt Cubs Initiative (DECI)**.
