# Quizzy — Quiz Management & Assessment Platform

Quizzy is a full-stack quiz web application built with the MERN stack. It provides an interactive platform where users can attempt multiple-choice quizzes, track their scores, and review their previous attempts, while administrators can manage quizzes, questions, and assessment results.

The application uses JWT-based authentication and supports CRUD operations for quiz and question management.

## Features

### Admin Dashboard

- **Authentication:** Secure admin login with validation and error handling.
- **Quiz Management:** Create, view, update, and delete quizzes.
- **Question Management:** Manage multiple-choice questions associated with each quiz.
- **Quiz Configuration:** Set quiz titles, optional descriptions, and timers.
- **Score Management:** View user scores across all quizzes or for a specific quiz.
- **Dashboard Overview:** Access relevant quiz and assessment information in one place.

### User Dashboard

- **Browse Quizzes:** View quizzes published by the administrator.
- **Attempt Quizzes:** Answer multiple-choice questions and submit quiz attempts.
- **Attempt Restrictions:** Prevent users from attempting a quiz more than once, where supported by the application logic.
- **Instant Score Review:** View scores after completing a quiz.
- **Attempt History:** Review previously attempted quizzes and their scores.
- **Dashboard Overview:** Access quiz-related information and previous results.

## Tech Stack

| Technology           | Purpose                            |
| -------------------- | ---------------------------------- |
| React.js             | Frontend user interface            |
| Node.js              | JavaScript runtime for the backend |
| Express.js           | Backend framework and REST APIs    |
| MongoDB              | Database                           |
| JSON Web Token (JWT) | Token-based authentication         |
| npm                  | Package and dependency management  |

## Project Structure

The project is organized into frontend and backend applications.

```text
Quizzy/
├── frontend/       # React application
├── backend/        # Express.js API and server
└── README.md
```

_Note: The structure above is illustrative. Update it if your actual repository uses a different layout._

## Getting Started

Follow these steps to run Quizzy locally.

### Prerequisites

Ensure that you have installed:

- [Node.js](https://nodejs.org/)
- npm (included with Node.js)
- [MongoDB](https://www.mongodb.com/) or a MongoDB Atlas connection

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Quizzy
```

Replace `<repository-url>` with the URL of the repository you are authorized to access.

### 2. Set Up the Backend

Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` directory:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secure_jwt_secret
```

Replace the placeholder values with your MongoDB connection string and a securely generated JWT secret.

Start the backend server:

```bash
npm run dev
```

The backend is expected to run at `http://localhost:3000`, provided that the server configuration uses this port.

### 3. Set Up the Frontend

Open another terminal in the project root and run:

```bash
cd frontend
npm install
npm run dev
```

The frontend is expected to be available at `http://localhost:5173` when using the default Vite development configuration.

### 4. Open the Application

Visit the frontend URL in your browser:

`http://localhost:5173`

Ensure the backend and MongoDB connection are running correctly.

## API Endpoints

The following endpoints describe the application's documented API.

### Authentication

| Method | Endpoint             | Description                                   |
| ------ | -------------------- | --------------------------------------------- |
| POST   | `/api/auth/register` | Register a user                               |
| POST   | `/api/auth/login`    | Authenticate a user or admin and return a JWT |

### Admin APIs

| Method | Endpoint                           | Description                                       |
| ------ | ---------------------------------- | ------------------------------------------------- |
| GET    | `/api/admin/quizzes`               | Retrieve all quizzes                              |
| POST   | `/api/admin/quizzes`               | Create a quiz                                     |
| PUT    | `/api/admin/quizzes/:id`           | Update a quiz                                     |
| DELETE | `/api/admin/quizzes/:id`           | Delete a quiz                                     |
| GET    | `/api/admin/quizzes/:id/questions` | Retrieve questions for a quiz                     |
| POST   | `/api/admin/quizzes/:id/questions` | Add a question to a quiz                          |
| PUT    | `/api/admin/questions/:id`         | Update a question                                 |
| DELETE | `/api/admin/questions/:id`         | Delete a question                                 |
| GET    | `/api/admin/scores`                | Retrieve user scores, optionally filtered by quiz |

### User APIs

| Method | Endpoint                   | Description                            |
| ------ | -------------------------- | -------------------------------------- |
| GET    | `/api/quizzes`             | Retrieve available quizzes             |
| POST   | `/api/quizzes/:id/attempt` | Submit or initiate a quiz attempt      |
| GET    | `/api/users/:id/attempts`  | Retrieve a user's quiz attempt history |

**Note:** Actual request bodies, response formats, authentication requirements, and endpoint behavior depend on the backend implementation.

## Authentication & Configuration

- JWT is used for token-based authentication.
- The backend uses environment variables for database connectivity and token signing.
- Keep `.env` files and secrets out of version control.
- Ensure that authorization checks protect administrator-only operations.

## Future Enhancements

Potential improvements include:

- Timed quizzes with a visible countdown.
- Detailed performance analytics and score summaries.
- Search, filtering, and category-based quiz discovery.
- Responsive UI improvements for mobile devices.
- More comprehensive validation and error handling.
- Automated tests for API endpoints and Authentication flows
