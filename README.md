# Chat-App-Redis

## 🚀 Overview

This is a real-time chat application built with a robust microservices architecture. It leverages Node.js (Express), TypeScript, MongoDB, Redis, and React to deliver a seamless and efficient chat experience. Key features include secure user authentication, instant real-time messaging, and comprehensive chat management capabilities.

## ✨ Features

-   **User Authentication**: Secure and streamlined user login and registration processes.
-   **Real-time Messaging**: Instant message delivery powered by WebSockets for a dynamic chat experience.
-   **Chat Management**: Create, manage, and organize both individual and group chats effortlessly.
-   **Microservices Architecture**: Backend services are independently deployed and managed (Chat, User, Mail) for enhanced scalability and maintainability.
-   **Scalable Design**: Utilizes Redis for efficient caching and robust message brokering, ensuring high performance and scalability.

## 🛠️ Technologies Used

### Backend

-   **Node.js**: Asynchronous event-driven JavaScript runtime.
-   **Express.js**: Fast, unopinionated, minimalist web framework for Node.js.
-   **TypeScript**: Statically typed superset of JavaScript for improved code quality and maintainability.
-   **MongoDB**: NoSQL database for flexible and scalable data storage.
-   **Mongoose**: Elegant MongoDB object modeling for Node.js.
-   **Redis**: In-memory data structure store, used for caching, session management, and message brokering.
-   **JWT (JSON Web Tokens)**: Compact, URL-safe means of representing claims to be transferred between two parties.
-   **Axios**: Promise-based HTTP client for making API requests.
-   **Dotenv**: Loads environment variables from a `.env` file.
-   **Nodemon**: Automatically restarts the Node.js application upon file changes.
-   **Concurrently**: Runs multiple npm scripts concurrently.

### Frontend

-   **React**: Declarative, efficient, and flexible JavaScript library for building user interfaces.
-   **Vite**: Next-generation frontend tooling for a fast development experience.
-   **TypeScript**: Enhances React components with type safety.
-   **Axios**: For seamless HTTP requests to the backend services.

## 📂 Project Structure

The project is organized into `backend` and `frontend` directories, reflecting its microservices architecture.

```
Chat-App-Redis/
├── backend/                  # Contains all microservices
│   ├── chat/                 # Handles chat creation, messages, and real-time communication
│   ├── mail/                 # Manages email functionalities (e.g., OTPs, notifications)
│   └── user/                 # Manages user authentication, profiles, and authorization
├── frontend/               # React-based single-page application
└── README.md               # Project documentation
```

## 📸 Screenshots

Here are some screenshots of the application in action:

### Chat Interface
![Chat Interface](screenshot/Screenshot%202025-07-26%20175714.png)

### User List
![User List](screenshot/Screenshot%202025-07-26%20175727.png)

### Login Page
![Login Page](screenshot/Screenshot%202025-07-26%20175756.png)

### Register Page
![Register Page](screenshot/Screenshot%202025-07-26%20175809.png)

### Chat with User
![Chat with User](screenshot/Screenshot%202025-07-26%20175836.png)

## ⚙️ Setup Instructions

### Prerequisites

Ensure you have the following installed:

-   Node.js (v14 or higher)
-   npm (Node Package Manager)
-   MongoDB instance (local or cloud-based, e.g., MongoDB Atlas)
-   Redis instance (local or cloud-based)

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Chat-App-Redis
```

### 2. Backend Setup

Navigate into each backend service directory (`backend/chat`, `backend/user`, `backend/mail`), install dependencies, and configure environment variables.

#### Common `.env` Variables for Backend Services

Create a `.env` file in each service directory (`backend/chat`, `backend/user`, `backend/mail`) with the following structure. Adjust values according to your setup.

```env
PORT=5000 # Or 5001, 5002, etc., for different services
MONGO_URI=mongodb://localhost:27017/chat_app # Your MongoDB connection string
JWT_SECRET=YOUR_SUPER_SECRET_JWT_KEY # A strong, unique secret key for JWT
REDIS_URL=redis://localhost:6379 # Your Redis connection URL

# Specific to Chat Service
USER_SERVICE=http://localhost:5000 # URL of the user service (adjust port if different)

# Specific to Mail Service (example - replace with your actual mail server details)
MAIL_HOST=smtp.ethereal.email
MAIL_PORT=587
MAIL_USER=your_email@example.com
MAIL_PASS=your_email_password
```

#### Install Dependencies and Build Each Service

```bash
# For Chat Service
cd backend/chat
npm install
npm run build

# For User Service
cd ../user
npm install
npm run build

# For Mail Service
cd ../mail
npm install
npm run build
```

### 3. Frontend Setup

Navigate to the `frontend` directory and install its dependencies.

```bash
cd frontend
npm install
```

#### Frontend `.env` Variables

Create a `.env` file in the `frontend` directory.

```env
VITE_BACKEND_URL=http://localhost:5000 # Adjust to your backend user service URL
```

## 🚀 Running the Application

### 1. Start Backend Services

Open three separate terminal windows. In each, navigate to a backend service directory and run the development server:

```bash
# Terminal 1: Chat Service
cd backend/chat
npm run dev

# Terminal 2: User Service
cd backend/user
npm run dev

# Terminal 3: Mail Service (if applicable and needed for your current testing)
cd backend/mail
npm run dev
```

### 2. Start Frontend Application

Open another terminal window, navigate to the `frontend` directory, and start the React development server:

```bash
cd frontend
npm run dev
```

The frontend application should now be accessible at `http://localhost:5173` (or another port if Vite assigns a different one). The backend services will be running on their configured ports (e.g., 5000, 5001, 5002).

## 🌐 API Endpoints (Examples)

### User Service

-   `POST /api/v1/user/register`: Register a new user.
-   `POST /api/v1/user/login`: Authenticate user and receive JWT.
-   `GET /api/v1/user/:id`: Retrieve user details by ID.

### Chat Service

-   `POST /api/v1/chat/create/chat`: Create a new chat conversation.
-   `GET /api/v1/chat/all`: Retrieve all chats for the authenticated user.
-   `POST /api/v1/chat/message/new`: Send a new message within a chat.

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repository, create a new branch, and submit pull requests. Please ensure your code adheres to the existing style and passes all tests.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.