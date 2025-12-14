# DevTinder 🚀

DevTinder is a full-stack web application inspired by Tinder, built for developers to connect, send connection requests, and manage profiles.

--------------------------------------------------

## 🛠 Tech Stack

Frontend:
- Vite + React
- Tailwind CSS
- DaisyUI
- React Router DOM
- Axios
- Redux Toolkit
- React Redux

Backend:
- Node.js
- Express.js
- MongoDB
- JWT Authentication
- CORS Middleware

--------------------------------------------------

## 📌 Features Implemented

### 🔹 Project Setup
- Created project using Vite + React
- Installed Tailwind CSS
- Installed DaisyUI

--------------------------------------------------

### 🔹 Routing & Layout
- Installed react-router-dom
- Configured BrowserRouter, Routes and nested Routes
- Created Body component with Outlet

Routes:
- /          → Feed
- /login     → Login Page
- /connections → My Connections
- /requests  → Connection Requests

--------------------------------------------------

### 🔹 Authentication
- Login Page implemented
- Axios installed for API calls
- Backend CORS configured with:
  - origin
  - credentials: true
- Every API call uses:
  axios({ withCredentials: true })
- JWT token handled via cookies
- Protected routes implemented
- Redirect user to /login if token is not present

--------------------------------------------------

### 🔹 Redux State Management
- Installed react-redux and @reduxjs/toolkit
- Setup Redux store using configureStore
- Created slices using createSlice
- Wrapped app with Provider
- Cached login user data in Redux store
- Used useDispatch and useSelector hooks
- Redux DevTools enabled
- Navbar updates instantly on login/logout

--------------------------------------------------

### 🔹 Feed & User Interaction
- Fetch feed from backend
- Store feed data in Redux
- Built user card component for feed display

--------------------------------------------------

### 🔹 Profile Management
- Edit Profile feature implemented
- Toast message shown on successful profile update

--------------------------------------------------

### 🔹 Connections
- View all accepted connections
- View all connection requests
- Accept / Reject connection requests

--------------------------------------------------

### 🔹 Logout
- Logout feature implemented
- Clear Redux store on logout
- Redirect user to login page

--------------------------------------------------

### 🔹 Code Refactoring
- Added constants file
- Created components folder
- Improved folder structure and readability

--------------------------------------------------

### 🔐 Route Protection Logic
- User cannot access protected routes without login
- Redirect to /login if JWT token is missing

--------------------------------------------------

## 📍 Routes Summary

/             → Feed  
/login        → Login  
/connections  → My Connections  
/requests     → Connection Requests  

--------------------------------------------------

## 👨‍💻 Author
Sandeep Adhikari

--------------------------------------------------

⭐ If you like this project, give it a star!

