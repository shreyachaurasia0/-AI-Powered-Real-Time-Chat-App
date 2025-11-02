# AI-Powered Real-Time Collaborative Coding Platform

## Project Overview

This is an advanced collaborative coding platform that combines real-time collaboration capabilities with AI assistance. Built on the MERN stack (MongoDB, Express.js, React, Node.js) with the integration of Redis Caching ,Socket.IO, it enables multiple developers to work together seamlessly while leveraging AI for code suggestions, documentation, and problem-solving.

## Technical Architecture

### Frontend Architecture (`frontend/`)

#### Core Technologies
- **React + Vite**: Utilizing React 18 with Vite for optimized development experience and fast builds
- **Tailwind CSS**: Implementing a utility-first CSS framework for responsive design
- **Socket.io-client**: Managing real-time bidirectional event-based communication
- **@webcontainer/api**: Enabling browser-based code execution in a secure environment

#### Key Frontend Components

1. **Authentication Module** (`src/auth/`)
   - `UserAuth.jsx`: Manages authentication state and user sessions
   - Implements JWT token management and secure storage
   - Handles automatic token refresh and session persistence

2. **Project Management** (`src/screens/`)
   - `Home.jsx`: Dashboard for project management
   - `Project.jsx`: Main workspace for collaborative coding
   - `FileExplorer.jsx`: Interactive file tree component

3. **Real-time Editor** (`src/components/`)
   - Monaco Editor integration for advanced code editing
   - Real-time collaboration using Operational Transformation
   - Syntax highlighting for multiple programming languages
   - Auto-completion and IntelliSense features

4. **State Management**
   - Context API for global state management
   - Custom hooks for real-time data synchronization
   - Optimistic updates for better user experience

### Backend Architecture (`backend/`)

#### Core Technologies
- **Express.js**: RESTful API implementation with middleware support
- **MongoDB**: Document database for flexible data storage
- **Socket.io**: Real-time event handling and broadcasting
- **Redis**: Session management and caching layer
- **Google's Generative AI**: AI-powered code assistance and suggestions

#### Key Backend Components

1. **API Layer** (`routes/`)
   - `user.routes.js`: Authentication and user management endpoints
   - `project.routes.js`: Project CRUD operations
   - `ai.routes.js`: AI assistance integration points

2. **Service Layer** (`services/`)
   - `user.service.js`: User management and authentication logic
   - `project.service.js`: Project operations and file management
   - `redis.service.js`: Cache and session management
   - `ai.service.js`: Integration with Google's Generative AI

3. **Data Layer** (`models/`)
   - `user.model.js`: User schema and methods
   - `project.model.js`: Project structure and relationships

4. **Middleware** (`middleware/`)
   - `auth.middleware.js`: JWT validation and role-based access control
   - `error.middleware.js`: Global error handling
   - `rate-limit.middleware.js`: API rate limiting

## Key Features

### 1. Authentication System
- User registration and login (`Register.jsx`, `Login.jsx`)
- JWT-based authentication (`auth.middleware.js`)
- Redis-based token blacklisting for logout

### 2. Project Management
- Create new projects
- Add collaborators to projects
- View all projects user has access to
- Real-time project synchronization
- File tree management

### 3. Code Editor Features
- Real-time code editing
- Syntax highlighting using highlight.js
- File tree visualization
- Multiple file support

### 4. Real-time Collaboration
- Socket.io based real-time updates
- Multiple users can work simultaneously
- Chat system between collaborators
- AI assistance (@ai mentions)

### 5. Code Execution
- Browser-based code execution using WebContainer API
- Live preview of running applications
- Package management support (npm)
- Real-time output streaming

## Key Components

### Frontend Components
1. `Project.jsx` - Main project workspace
2. `Home.jsx` - Project listing and creation
3. `UserAuth.jsx` - Authentication wrapper

### Backend Services
1. `ai.service.js` - AI assistance using Gemini
2. `project.service.js` - Project management
3. `user.service.js` - User management
4. `redis.service.js` - Session management

## Data Models

### User Model (`user.model.js`)
```javascript
{
    email: String,
    password: String (hashed)
}
```

### Project Model (`project.model.js`)
```javascript
{
    name: String,
    users: [ObjectId],
    fileTree: Object
}
```

## Environment Setup
Required environment variables:

### Backend (.env)
```properties
PORT=3000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_AI_KEY=your_gemini_api_key
REDIS_HOST=your_redis_host
REDIS_PORT=your_redis_port
REDIS_PASSWORD=your_redis_password
```

### Frontend (.env)
```properties
VITE_API_URL=http://localhost:3000
```

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- MongoDB
- Redis
- Google Cloud Account with Gemini API access

### Running the Project

1. Backend Setup:
```bash
cd backend
npm install
npm start
```

2. Frontend Setup:
```bash
cd frontend
npm install
npm run dev
```

3. Access the application at `http://localhost:5173`

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.
