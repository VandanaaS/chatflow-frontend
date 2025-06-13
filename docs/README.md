
# ChatFlow - MERN Real-Time Messaging App

## Overview

ChatFlow is a real-time messaging application similar to WhatsApp, built using the MERN stack. 
The focus is clean code, scalable architecture, real-time messaging, and technical system design.

## Tech Stack

- Frontend: React, Bootstrap, Axios, React Router, Socket.io Client
- Backend: Node.js, Express, Socket.io, MongoDB Atlas, Mongoose
- Authentication: JWT (JSON Web Tokens)

## Features

- User Registration & Login
- Real-time messaging with Socket.io
- REST API for backend services
- MongoDB Atlas cloud-hosted database
- Basic Bootstrap UI styling
- Fully scalable architecture

## Setup Instructions

### Backend

```bash
cd backend
npm install
# Add .env with MONGO_URI and JWT_SECRET
node server.js
```

### Frontend

```bash
cd frontend
npm install
npm start
```

## Demo Flow

- Register at `/register`
- Login at `/login`
- Chat in `/`
- Test real-time behavior by opening multiple browser tabs

