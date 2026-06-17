Empify
Empify is an Employee management platform built with a React + Vite frontend and a Node.js + Express backend. It supports admin and employee workflows for attendance, leave management, payslip generation, profile management, and employee administration.

🚀 Key Features
Admin Features
Admin login and session authentication
Employee management
Add new employees
Edit employee details
Soft delete employees
Dashboard metrics
Total employees
Today’s attendance count
Pending leave requests
Department overview
Leave management
View all leave requests
Approve / reject / manage leave status
Payslip management
Create payslips for employees
View all payslips
Employee Features
Employee login and session management
Attendance tracking
Check in
Check out
Automatic working hours calculation
Leave application
Submit leave requests with future date validation
View leave history and status
Payslip view
Access generated payslips
Print payslips by ID
Profile management
View profile details
Update profile bio
Change password
Personalized dashboard
Employee attendance summary
Pending leave count
Latest payslip preview
🧱 Technology Stack
Backend
Node.js + Express
MongoDB via Mongoose
JSON Web Tokens (JWT) for auth
bcrypt for password hashing
dotenv for environment variables
cors for cross-origin requests
multer for request parsing
inngest for event-based workflows
nodemon for development auto-reload
Frontend
React
Vite
Tailwind CSS
React Router
Axios
react-hot-toast
lucide-react icons
date-fns for date utilities
📁 Project Structure
Backend
backend/server.js — Express server and route registration
backend/config/db.js — MongoDB connection logic
backend/routes/ — API route definitions for auth, employees, profile, attendance, leave, payslips, and dashboard
backend/controllers/ — Business logic and request handlers
backend/models/ — Mongoose models for User, Employee, Attendance, LeaveApplication, Payslip
backend/middleware/auth.js — JWT-protected routes and admin guard
backend/inngest/ — Event handlers and background workflow integration
Frontend
frontend/src/App.jsx — Application routes and layout
frontend/src/api/axios.js — Axios client configuration
frontend/src/pages/ — Page views for dashboard, employees, attendance, leave, payslips, settings, and login
frontend/src/components/ — Reusable UI components and forms
frontend/src/context/AuthContext.jsx — Authentication state management
frontend/src/assets/assets.jsx — Shared UI data and constants
Empify/
│
├── backend/
│   ├── config/
│   │   └── db.js
│   │
│   ├── controllers/
│   │
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │
│   ├── routes/
│   │
│   ├── inngest/
│   │
│   ├── .env
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── public/
│   │
│   ├── src/
│   │   ├── api/
│   │   │   └── axios.js
│   │   │
│   │   ├── assets/
│   │   │
│   │   ├── components/
│   │   │
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   │
│   │   ├── pages/
│   │   │
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
├── README.md
└── package-lock.json
⚙️ How It Works
Backend Flow
The frontend sends HTTP requests to Express API endpoints under /api/*.
auth.js middleware verifies JWT tokens on protected routes.
The backend reads and writes data to MongoDB using Mongoose models.
Admin operations such as employee creation, payslip generation, and leave approval are routed through admin-specific controllers.
Employee-specific data like attendance, leave history, and payslips are filtered by the authenticated user’s userId.
Event-driven notifications and processing use Inngest for background workflows.
Frontend Flow
Users navigate to /login/admin or /login/employee.
The login form posts credentials to /api/auth/login.
After successful authentication, a JWT token is stored and used on future API requests.
Protected pages load an authenticated user session and render either an admin dashboard or employee dashboard.
UI actions such as adding employees, clocking attendance, applying leave, and generating payslips use Axios to call backend APIs.
The app uses Tailwind CSS for responsive UI and React Router for page navigation.
🛠️ Setup Instructions
Backend
Open a terminal in backend/
Install dependencies:
npm install
Create a .env file with:
MONGO_URI=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
Start the backend server:
npm run server
Frontend
Open a terminal in frontend/
Install dependencies:
npm install
Start the frontend:
npm run dev
Default URLs
Frontend: http://localhost:5173 (default Vite port)
Backend: http://localhost:4000
🔐 Authentication
Auth endpoint: POST /api/auth/login
Session endpoint: GET /api/auth/session
Protected endpoints require header: Authorization: Bearer <token>
Password hashing: bcrypt
Token expiry: 7 days
