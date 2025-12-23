# 💬 Chat App Fullstack

A real-time chat application built with the MERN stack (MongoDB, Express. js, React. js, Node.js) featuring modern UI/UX and WebSocket communication.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-v18+-green.svg)
![React](https://img.shields.io/badge/React-v18+-blue.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-v6+-green.svg)

## ✨ Features

- 🔐 **User Authentication** - Secure signup/login with JWT
- 💬 **Real-time Messaging** - Instant message delivery using Socket.io
- 👥 **User Management** - User profiles and online status
- 🖼️ **Media Sharing** - Share images and files
- 🔔 **Notifications** - Real-time message notifications
- 📱 **Responsive Design** - Works seamlessly on desktop and mobile
- 🌙 **Dark Mode** - Eye-friendly dark theme support
- ✅ **Message Status** - Read receipts and delivery status
- 🔍 **Search** - Search for users and conversations

## 🛠️ Tech Stack

### Frontend
- **React. js** - UI library
- **Redux/Context API** - State management
- **Socket.io-client** - Real-time communication
- **Axios** - HTTP client
- **React Router** - Navigation
- **Tailwind CSS / Material-UI** - Styling

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - ODM for MongoDB
- **Socket.io** - WebSocket library
- **JWT** - Authentication
- **Bcrypt** - Password hashing

## 📋 Prerequisites

Before running this project, make sure you have: 

- **Node.js** (v18 or higher)
- **MongoDB** (v6 or higher)
- **npm** or **yarn** package manager

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/PhanNhatTien090/Chat-App-Fullstack-.git
cd Chat-App-Fullstack-
```

### 2. Install Backend Dependencies

```bash
cd backend
npm install
```

### 3. Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

### 4. Environment Variables

Create a `.env` file in the `backend` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/chatapp
# Or use MongoDB Atlas
# MONGODB_URI=mongodb+srv://<username>:<password>@cluster. mongodb.net/chatapp

# JWT Secret
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRE=7d

# Client URL (for CORS)
CLIENT_URL=http://localhost:3000

# File Upload (Optional)
MAX_FILE_SIZE=5242880
UPLOAD_PATH=./uploads
```

Create a `.env` file in the `frontend` directory:

```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_SOCKET_URL=http://localhost:5000
```

## 🏃 Running the Application

### Development Mode

**Terminal 1 - Backend:**
```bash
cd backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm start
```

The application will be available at: 
- Frontend: `http://localhost:3000`
- Backend API: `http://localhost:5000`

### Production Build

**Backend:**
```bash
cd backend
npm start
```

**Frontend:**
```bash
cd frontend
npm run build
npm install -g serve
serve -s build
```

## 📁 Project Structure

```
Chat-App-Fullstack-/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── messageController.js
│   │   └── userController.js
│   ├── middleware/
│   │   ├── auth.js
│   │   └── errorHandler.js
│   ├── models/
│   │   ├── User.js
│   │   ├── Message.js
│   │   └── Conversation.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── messages.js
│   │   └── users.js
│   ├── socket/
│   │   └── socketHandler.js
│   ├── uploads/
│   ├── . env
│   ├── server.js
│   └── package.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Chat/
│   │   │   ├── Auth/
│   │   │   ├── Sidebar/
│   │   │   └── Common/
│   │   ├── context/
│   │   │   ├── AuthContext.js
│   │   │   └── SocketContext.js
│   │   ├── pages/
│   │   │   ├── Login. js
│   │   │   ├── Register.js
│   │   │   └── Chat.js
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── utils/
│   │   ├── App.js
│   │   └── index.js
│   ├── . env
│   └── package. json
│
└── README. md
```

## 🔌 API Endpoints

### Authentication
```
POST   /api/auth/register     - Register new user
POST   /api/auth/login        - Login user
GET    /api/auth/me           - Get current user
POST   /api/auth/logout       - Logout user
```

### Users
```
GET    /api/users             - Get all users
GET    /api/users/:id         - Get user by ID
PUT    /api/users/:id         - Update user profile
```

### Messages
```
GET    /api/messages/: conversationId    - Get messages
POST   /api/messages                    - Send message
DELETE /api/messages/:id                - Delete message
```

### Conversations
```
GET    /api/conversations                - Get all conversations
POST   /api/conversations                - Create conversation
GET    /api/conversations/: id            - Get conversation by ID
```

## 🔄 Socket Events

### Client to Server
- `join` - Join a conversation room
- `sendMessage` - Send a new message
- `typing` - User is typing
- `stopTyping` - User stopped typing

### Server to Client
- `receiveMessage` - Receive new message
- `userOnline` - User came online
- `userOffline` - User went offline
- `typing` - Show typing indicator
- `stopTyping` - Hide typing indicator

## 🧪 Testing

```bash
# Run backend tests
cd backend
npm test

# Run frontend tests
cd frontend
npm test
```

## 🚢 Deployment

### Deploy to Heroku

**Backend:**
```bash
cd backend
heroku create your-app-name-api
git push heroku main
```

**Frontend:**
```bash
cd frontend
npm run build
# Deploy to Netlify, Vercel, or similar
```

### Deploy to Render/Railway

1. Connect your GitHub repository
2. Set environment variables
3. Deploy both frontend and backend

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Phan Nhật Tiến**

- GitHub: [@PhanNhatTien090](https://github.com/PhanNhatTien090)

## 🙏 Acknowledgments

- Socket.io for real-time communication
- MongoDB for the database
- React community for amazing tools and libraries

## 📧 Contact

For any questions or suggestions, please reach out: 

- Email: your.email@example.com
- Project Link: [https://github.com/PhanNhatTien090/Chat-App-Fullstack-](https://github.com/PhanNhatTien090/Chat-App-Fullstack-)

---

⭐️ If you like this project, please give it a star on GitHub! 
```
