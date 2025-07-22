# ⚡ Real-Time Chat Application (MERN + WebSockets)

A high-performance, full-stack chat application built with the **MERN** stack (MongoDB, Express.js, React.js, Node.js) and **Socket.io** for real-time, ultra-low-latency messaging. This project is architected for instant communication and scalable, event-driven data flows, making it a learning model for financial, HFT, or any real-time data streaming use case.

---

## 🏗️ Architecture Overview

- **Backend:** Node.js + Express.js REST API with Socket.io for real-time communication, JWT authentication, image uploads via Cloudinary, and MongoDB for data storage.
- **Frontend:** React.js SPA with real-time messaging via Socket.io.
- **Database:** MongoDB for persistent user and message data.

---

## 🚀 Key Features

- **Ultra-Low-Latency Messaging:** Real-time chat using WebSockets (Socket.io), ensuring messages are delivered instantly between users.
- **Event-Driven Backend:** Efficient, scalable event-driven server design, suitable for high-throughput applications.
- **Authentication & Security:** JWT-based authentication with HTTP-only cookies for session management.
- **User Profiles & Image Upload:** Users can update their profile with avatars, stored via Cloudinary.
- **Persistent Chat History:** MongoDB stores all messages and user data securely.
- **Real-Time Notifications:** Instant typing indicators and message delivery alerts.
- **Scalable to Multiple Users:** Handles many concurrent users and conversations.
- **Production Ready:** Environment variable support and static file serving for production deployment.

---

## 🖥️ Demo

🌍 **Live Demo:** [https://chatapp-fdps.onrender.com](https://chatapp-fdps.onrender.com)

---

## 📦 Tech Stack

### Backend
- **Node.js**
- **Express.js**
- **Socket.io** (WebSockets)
- **JWT** (jsonwebtoken)
- **MongoDB** (mongoose)
- **Cloudinary** (for image uploads)
- **bcryptjs** (for password hashing)

### Frontend
- **React.js**
- **Socket.io-client**

---

## 📂 Project Structure

```
Real-Time-Chat-Application/
│
├── backend/
│   ├── src/
│   │   ├── controllers/      # Auth, Message controllers
│   │   ├── lib/              # Cloudinary, DB, Socket.io utils
│   │   ├── models/           # Mongoose schemas
│   │   ├── routes/           # Route definitions
│   │   └── index.js          # Entry point
│   ├── package.json
│   └── package-lock.json
│
├── frontend/
│   └── ...                   # React app source code
│
└── README.md
```

---

## ⚙️ Backend Environment Variables

Create a `.env` file in the `backend` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
NODE_ENV=development
```

---

## 🏃‍♂️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/arpitKSi/Real-Time-Chat-Application.git
cd Real-Time-Chat-Application
```

### 2. Install Backend Dependencies

```bash
cd backend
npm install
```

### 3. Set Up Environment Variables

Add a `.env` file in `backend/` as shown above.

### 4. Start the Backend Server

```bash
npm run dev
```
Server runs on `http://localhost:5000` by default.

### 5. Install and Run Frontend

> **Note:** The frontend source code is in the `frontend/` folder. Install dependencies and run the dev server as per its README or setup instructions.

---

## 🛡️ API Overview

### Authentication

- `POST /api/auth/signup` — Register new users
- `POST /api/auth/login` — User login
- `POST /api/auth/logout` — User logout
- `PUT /api/auth/update-profile` — Update user profile picture (Cloudinary upload)
- `GET /api/auth/check-auth` — Check current authentication status

### Messaging

- `GET /api/messages/users` — Get all users (except self)
- `GET /api/messages/:id` — Get messages between logged-in user and user with `:id`
- `POST /api/messages/:id` — Send a message (optionally with image) to user `:id`

---

## 💬 Real-Time Communication (Socket.io)

- **Connection Handling:** Users get a unique socket on login.
- **Events:**
  - `newMessage` — Real-time delivery of new messages.
  - Typing indicators and other real-time UI updates.

---

## 🛠️ Core Code Highlights

- **JWT Auth:** Secure, HTTP-only cookie storage for tokens (`lib/utils.js`).
- **Password Hashing:** bcryptjs for secure password storage (`auth.controller.js`).
- **Cloudinary Integration:** For storing and serving profile images and chat images (`lib/cloudinary.js`).
- **Socket.io Server:** Centralized in `lib/socket.js` for scalability and multi-user support.
- **CORS:** Configured for local development (`http://localhost:5173`) and production use.

---

## 🧑‍💻 Example Usage

**Signup:**
```json
POST /api/auth/signup
{
  "fullName": "Alice Smith",
  "email": "alice@example.com",
  "password": "password123"
}
```

**Send Message:**
```json
POST /api/messages/:receiverId
{
  "text": "Hello!",
  "image": "<base64 string, optional>"
}
```

---

## 🚧 Future Improvements

- Group chat and channels
- Message read receipts and delivery status
- Enhanced user search and contacts
- Push notification integration
- Message encryption at rest
- Dockerization and CI/CD

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

---

## 📝 License

This project is [ISC Licensed].


## 📬 Contact

For questions, issues, or feature requests, please [open an issue](https://github.com/arpitKSi/Real-Time-Chat-Application/issues) or contact [@arpitKSi](https://github.com/arpitKSi).

---
