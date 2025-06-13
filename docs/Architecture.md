
# Architecture Overview

## System Flow

[ React Frontend ] <--> [ Node.js Backend (Express + Socket.io) ] <--> [ MongoDB Atlas ]

- WebSockets power real-time chat via Socket.io.
- RESTful APIs for authentication, conversations, and message management.
- JWT-based authentication.

## Data Models

### User
- _id
- username
- email
- hashed password
- createdAt

### Conversation
- _id
- participants [UserId]
- createdAt

### Message
- _id
- conversationId
- senderId
- content
- timestamp

## Scaling Plan

- MongoDB Atlas Sharding
- Redis pub/sub adapter for Socket.io multi-instance scaling
- Stateless APIs load-balanced with multiple Node.js instances
- CDN hosted frontend

