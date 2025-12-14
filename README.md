DevTinder Backend 🚀
A Microservices-Inspired Backend for Developer Connections
Node.js Express.js MongoDB License: MIT

📌 Overview
DevTinder is a MERN stack web application designed to help developers connect and collaborate, similar to popular dating apps but tailored specifically for the tech community. Users can create profiles, explore suggested developers, send connection requests, and manage their matches.

This repository contains the fully functional and scalable backend of DevTinder. It is built with Node.js, Express, and MongoDB, following a microservices architectural pattern to ensure maintainability and future scaling.

🛠️ Tech Stack
Category	Technology	Description
Backend Framework	Node.js + Express.js	Runtime environment and minimal, flexible framework for the API.
Database	MongoDB + Mongoose	NoSQL database and an ODM for elegant data modeling.
Authentication	JWT (JSON Web Tokens)	Secure, state-less authentication using tokens stored in HTTP-only cookies.
Encryption	bcryptjs	For securely hashing and salting user passwords.
Utilities	dotenv	For managing environment variables securely.
Testing	Postman	Used for comprehensive API testing and documentation.
🔑 Features Implemented
1. Robust Authentication System
✅ User Signup, Login, and Logout functionality.
✅ JWT-based authentication with secure cookies.
✅ Password encryption using bcryptjs.
✅ Authentication middleware to protect all private routes.
2. User Profile Management
✅ View and Edit user profile details (with security-restricted fields).
✅ Secure Update Password functionality with validation.
3. Connection Request System
✅ Send connection requests (Interested or Ignored status).
✅ Accept or Reject received requests.
✅ Prevent duplicate requests using MongoDB validation.
✅ Prevent self-requests using Mongoose .pre middleware.
4. Optimized Feed API & Pagination (The Core Feature)
✅ Fetches suggested developer profiles while intelligently excluding:
The logged-in user.
Existing connections.
Users with pending requests.
Previously Ignored users.
✅ Implemented pagination using skip & limit for performance.
✅ Optimized query using MongoDB $nin and $ne operators.
5. Database Design & Optimization
User Schema: Includes sanitized input fields (trim, lowercase), unique constraints on email and username.
ConnectionRequest Schema: Defines fromUserId, toUserId, and status with an enum validation.
Advanced Query Optimization: Used Indexes (index: true) and Compound Indexes on critical fields for faster query execution.
6. Middleware Implementation
Authentication Middleware: Ensures only authenticated users access protected resources.
Error Handling Middleware: Centralized system for consistent error responses.
Mongoose Pre-Hook Middleware: Custom logic to prevent self-requests before saving to the database.
🚀 API Endpoints
The APIs are modularly structured into separate routers (auth, profile, connections, users) for high maintainability.

Category	Method	Endpoint	Description	Auth Required
Auth	POST	/auth/signup	Register a new user	❌
Auth	POST	/auth/login	Authenticate user & issue JWT	❌
Auth	POST	/auth/logout	Logout user by clearing JWT cookie	✅
Profile	GET	/profile/view	Get logged-in user profile	✅
Profile	PATCH	/profile/edit	Update allowed profile fields	✅
Feed	GET	/user/feed?page=1&limit=10	Get suggested developer profiles with pagination	✅
Requests	POST	/request/send/:status/:toUserId	Send a connection request (Interested/Ignored)	✅
Requests	POST	/request/review/:status/:requestId	Accept/Reject a received request	✅
Requests	GET	/user/requests/received	Fetch pending connection requests	✅
Requests	GET	/user/connections	Fetch accepted connections (matches)	✅
