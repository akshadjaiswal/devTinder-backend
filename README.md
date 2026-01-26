# DevTinder Backend 🚀

## 📌 Overview
DevTinder is a **MERN stack** web application designed to help developers **connect and collaborate**, similar to Tinder but specifically for developers. Users can create profiles, explore other developers, send connection requests, and manage their matches.

This repository contains the **backend** of DevTinder, built with **Node.js, Express, and MongoDB**, following a **microservices architecture** for scalability.

> ⚠️ **Note:** The backend is **fully functional** and ready for further scaling and optimizations.

---

## 📖 My Node.js Learning Repository
I learned and maintained all my Node.js knowledge in one place:
[**Namsate Nodejs**](https://github.com/akshadjaiswal/Namaste-Nodejs)


## 🛠️ Tech Stack
- **Backend Framework**: [Node.js](https://nodejs.org/en) + [Express.js](https://expressjs.com/)
- **Database**: [MongoDB](https://www.mongodb.com/) + [Mongoose](https://mongoosejs.com/)
- **Authentication**: [JWT (JSON Web Tokens)](https://jwt.io/) + Cookies
- **Encryption**: [bcryptjs](https://www.npmjs.com/package/bcryptjs) for password hashing
- **API Testing**: Postman
- **Environment Variables Management**: dotenv
- **Package Manager**: npm

---

## 🔑 Features Implemented

### **1. Authentication System**
✅ User Signup, Login, and Logout  
✅ JWT-based authentication with secure cookies  
✅ Password encryption using **bcryptjs**  
✅ Authentication middleware to protect routes  

### **2. User Profile Management**
✅ View user profile  
✅ Edit profile details (restricted fields for security)  
✅ Update password with validation  

### **3. Connection Request System**
✅ Send connection requests (`Interested` or `Ignored`)  
✅ Accept or reject received requests  
✅ Prevent duplicate requests using MongoDB validation  
✅ Prevent self-requests using Mongoose `.pre` middleware  

### **4. Feed API & Pagination**
✅ Fetch suggested developers while excluding:  
   - Logged-in user  
   - Existing connections  
   - Ignored users  
   - Users with pending requests  
✅ Implemented **pagination** using `skip` & `limit`  
✅ Optimized query using **MongoDB $nin and $ne operators**  

### **5. Database Design**
✅ **User Schema**:
   - Sanitized input fields (`trim`, `lowercase`, validation)
   - Unique constraints on email and username  

✅ **ConnectionRequest Schema**:
   - `fromUserId`, `toUserId`, `status` with **enum validation**
   - Indexed fields for optimized queries  
   - Prevents multiple requests between the same users  

### **6. Advanced Query Optimization**
✅ **Indexes & Compound Indexes**:
   - Used `index: true` for faster queries  
   - Implemented compound indexes to optimize search  

### **7. Middleware Implementation**
✅ **Authentication Middleware**: Protects private routes  
✅ **Error Handling Middleware**: Centralized error response  
✅ **Mongoose `.pre` Middleware**: Prevents self-requests  

### **8. Express Router Structure**
✅ Modular route organization for maintainability  
✅ APIs structured into separate routers (`auth`, `profile`, `connections`, `users`)  

---

## 🚀 API Endpoints

### **1️⃣ Authentication Routes**
| Method | Endpoint      | Description          | Auth Required |
|--------|--------------|----------------------|--------------|
| POST   | `/auth/signup` | Register a new user | ❌ |
| POST   | `/auth/login` | Authenticate user & issue JWT | ❌ |
| POST   | `/auth/logout` | Logout user by clearing JWT cookie | ✅ |

---

### **2️⃣ User Profile Routes**
| Method | Endpoint           | Description              | Auth Required |
|--------|-------------------|------------------------|--------------|
| GET    | `/profile/view`   | Get logged-in user profile | ✅ |
| PATCH  | `/profile/edit`   | Update allowed profile fields | ✅ |
| PATCH  | `/profile/password` | Update user password | ✅ |

---

### **3️⃣ Connection Request Routes**
| Method | Endpoint                                    | Description                 | Auth Required |
|--------|--------------------------------------------|-----------------------------|--------------|
| POST   | `/request/send/:status/:toUserId`         | Send a connection request (Interested/Ignored) | ✅ |
| POST   | `/request/review/:status/:requestId`      | Accept/Reject a request | ✅ |
| GET    | `/user/requests/received`                 | Fetch pending connection requests | ✅ |
| GET    | `/user/connections`                       | Fetch accepted connections | ✅ |

---

### **4️⃣ Feed API & Pagination**
| Method | Endpoint      | Description                              | Auth Required |
|--------|--------------|----------------------------------------|--------------|
| GET    | `/user/feed?page=1&limit=10` | Get suggested developer profiles with pagination | ✅ |

---

## 🏗️ Setup & Running the Server

### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/akshadjaiswal/devTinder-backend.git
cd devTinder-backend
```

### **2️⃣ Set Up Environment Variables**
Create a `.env` file and add:
```ini
DATABASE_URL=mongodb+srv://<username>:<password>@cluster0.mongodb.net/devTinder
JWT_SECRET=your_jwt_secret
PORT=3000
```

### **3️⃣ Start the Backend Server**
```bash
npm start
```
Server runs at: `http://localhost:3000/`

---

## 🔗 Frontend Integration
The frontend for DevTinder is available at:
🔗 **[DevTinder Frontend Repository](https://github.com/akshadjaiswal/devTinder-frontend)**

Make sure the backend is running before accessing the frontend.

---
## Learning Resources

Explore my additional repositories to deepen your understanding of related topics in the JavaScript ecosystem:

- [Namaste Javascript](https://github.com/akshadjaiswal/Namaste-Javascript): A repository focused on learning Javascript concepts, from basics to advanced programming.
- [Namaste React](https://github.com/akshadjaiswal/Namaste-React): A repository dedicated to mastering React.js, covering foundational and advanced aspects of building interactive UIs.

---

## 📢 Contribution Guidelines
Since the project is now fully functional, improvements are still welcome!
✅ Feel free to open issues for bugs or feature requests.  
✅ Fork the repository and submit a pull request.  

---

## 📌 Future Enhancements
🔹 Real-time notifications using WebSockets  
🔹 Messaging System for better user interaction  
🔹 Profile Search & Filtering  
🔹 Unit Testing for API reliability  

---

## 📜 License
This project is open-source and available under the **MIT License**.

---

<div align="center">

**Made with ❤️ by Akshad Jaiswal**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/akshadjaiswal)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/akshadsantoshjaiswal)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/akshad_999)

</div>


