#  Broken Authentication Assignment

This project implements a **multi-step authentication system** using Node.js and Express.
It demonstrates secure authentication techniques including **login, OTP verification, JWT token generation, and protected routes**.

The assignment simulates a real-world backend authentication flow used in modern web applications.

---

##  Features

* User login with **email and password**
* **OTP verification system**
* **Session management using cookies**
* **JWT access token generation**
* **Protected routes using authentication middleware**
* API request logging middleware
* Simple mock user database

---

## 🛠 Tech Stack

* Node.js
* Express.js
* JSON Web Tokens (JWT)
* Cookie Parser
* Thunder Client (API testing)

---

##  Project Structure

```
broken-auth-assignment
│
├── middleware
│   ├── auth.js
│   └── logger.js
│
├── utils
│   ├── mockDb.js
│   └── tokenGenerator.js
│
├── server.js
├── package.json
├── README.md
└── .env.example
```

---

##  Installation

### 1. Clone the repository

```
git clone https://github.com/kaushal-dev928/broken-auth-assignment
```

### 2. Navigate to project folder

```
cd backend
```

### 3. Install dependencies

```
npm install
```

### 4. Create `.env` file

Create a `.env` file in the root directory and add:

```
PORT=3000
JWT_SECRET=my_super_secret_key
APPLICATION_SECRET=app_secret_123
```

### 5. Run the server

```
node server.js
```

Server will run at:

```
http://localhost:3000
```

---

##  Authentication Flow

### 1️⃣ Login

```
POST /auth/login
```

Body:

```
{
  "email": "test@example.com",
  "password": "password123"
}
```

Response returns a **loginSessionId and OTP**.

---

### 2️⃣ Verify OTP

```
POST /auth/verify-otp
```

Body:

```
{
  "loginSessionId": "SESSION_ID",
  "otp": "OTP_CODE"
}
```

A **session cookie** will be created after successful verification.

---

### 3️⃣ Generate Access Token

```
POST /auth/token
```

Response:

```
{
  "access_token": "JWT_TOKEN",
  "expires_in": 900
}
```

---

### 4️⃣ Access Protected Route

```
GET /protected
```

Header:

```
Authorization: Bearer JWT_TOKEN
```

Response:

```
{
 "message": "Access granted",
 "success_flag": "FLAG-xxxx"
}
```

---

##  Testing

All endpoints were tested using **Thunder Client (VS Code extension)**.

Steps tested:

1. Login endpoint
2. OTP verification
3. Token generation
4. Accessing protected route

---

##  Security Concepts Demonstrated

* JWT Authentication
* OTP Verification
* Session Management
* Middleware-based Route Protection
* API Logging

---

##  Example Test User

```
Email: test@example.com
Password: password123
```

---

##  Future Improvements

* Replace in-memory storage with a real database
* Implement password hashing using bcrypt
* Send OTP via email or SMS
* Add refresh token system
* Add rate limiting and login protection

---

## 👨‍💻 Author

Kaushal Ghongade
MERN Stack Developer
