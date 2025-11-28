# Whisper Chat API

Backend API for a real-time chat application built with Python, supporting public groups and private conversations with a robust permission system and WebSocket integration.

## Features

### 🔐 Authentication & Security
- **JWT-based authentication** (signup, login, logout)
- **Password policy enforcement**:
  - Minimum 8 characters
  - Requires uppercase, lowercase, numbers, and special characters
  - Prevents reuse of last 5 passwords
- Secure password hashing with bcrypt
- **Custom JWT Middleware for WebSockets** - Secure real-time communication

### Custom JWT Middleware
- Validates JWT tokens for WebSocket connections
- Checks token blacklist status
- Sets user object in WebSocket scope

### 💬 Chat Features
- **Public Groups**: Join/leave public chat rooms
- **Private Conversations**: One-on-one private messaging
- **Real-time Messaging**: WebSocket-based instant messaging
- Message history and persistence
- **Typing/Not Typing Indicators** - Real-time typing status via WebSockets

### 🛡️ Group Permission System

#### Group Owner Permissions:
- Create and delete groups
- Modify group name and information
- Assign/remove administrators
- Kick admins and regular members
- Manage group settings

#### Administrator Permissions:
- Kick regular members
- Assist in group moderation
- Access enhanced group management tools

#### Member Permissions:
- Send messages in groups
- Join/leave public groups
- View group members and information
- Get all direct messages (DMs)
- Get all joined groups

### 🔄 Messages API with WebSocket Integration
- **RESTful Messages API** - Complete CRUD operations for messages
- **Real-time WebSocket Integration** - Instant message delivery
- **Seamless API-WS Sync** - Messages created via API broadcast via WebSockets
- **Dual Communication Channels** - Support for both HTTP and WebSocket messaging