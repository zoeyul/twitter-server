# twitter server

### 🛠 Tech Stack & Implementation
- Framework: Express.js
- Database Integration (Multi-branch Testing):
- Tested various DB/ORM combinations across dedicated branches:
  - Main: Sequelize (SQL ORM)
  - feature/mysql: Raw MySQL
  - feature/mongodb: Raw MongoDB
  - feature/mongoose: Mongoose (NoSQL ODM)
- Real-time Features: Integrated Socket.io for instant tweet updates and feed synchronization.
- Validation: Implemented strict input validation for all API endpoints.

### 🔒 Security & Performance
- Security Hardening: * Implemented protections against XSS (Cross-Site Scripting) and CSRF (Cross-Site Request Forgery).
- Traffic Management: Configured Rate Limiting to prevent API abuse and ensure server stability.

### 📡 API Specifications
#### **1. Authentication**

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/auth/signup` | Register a new user account |
| `POST` | `/auth/login` | Authenticate user and issue session/token |
| `POST` | `/auth/logout` | Invalidate current user session |

#### **2. Tweets**
Real-time updates are supported via Socket.io when creating new tweets.

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/tweets` | Fetch all tweets from the database |
| `GET` | `/tweets?username=:username` | Filter and fetch tweets by a specific username |
| `GET` | `/tweets/:id` | Fetch detailed information of a single tweet |
| `POST` | `/tweets` | Create a new tweet (Broadcasts via Socket.io) |
| `PUT` | `/tweets/:id` | Update the content of an existing tweet |
| `DELETE` | `/tweets/:id` | Permanently remove a tweet |
