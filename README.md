# TaskFlow - Modern Task Management Application

A full-stack task management application built with React, Node.js, Express, and MongoDB. Features secure JWT authentication, real-time task management, and a clean, responsive UI.

## Features

- **Secure Authentication System**
  - User registration with email validation
  - JWT-based authentication
  - Secure password hashing with bcrypt
  - Protected routes and API endpoints

- **Task Management**
  - Create, read, update, and delete tasks
  - Mark tasks as pending or completed
  - Filter tasks by status
  - User-specific task isolation

- **Modern UI/UX**
  - Clean, responsive design with Tailwind CSS
  - Dark mode support
  - Loading states and error handling
  - Form validation with user feedback

## Tech Stack

**Frontend**
- React 18 with Vite
- Tailwind CSS for styling
- Axios for API requests
- React Router for navigation

**Backend**
- Node.js with Express
- MongoDB with Mongoose ODM
- JWT for authentication
- bcrypt for password hashing
- Express Validator for input validation

**Database**
- MongoDB (local or MongoDB Atlas)

## Project Structure

```
taskflow/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── middleware/
│   │   └── auth.js
│   ├── models/
│   │   ├── User.js
│   │   └── Task.js
│   ├── routes/
│   │   ├── auth.js
│   │   └── tasks.js
│   ├── .env.example
│   ├── server.js
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── context/
│   │   ├── utils/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env.example
│   ├── index.html
│   ├── package.json
│   └── tailwind.config.js
└── README.md
```

## Local Setup

### Prerequisites

- Node.js (v16 or higher)
- MongoDB (local installation or MongoDB Atlas account)
- npm or yarn

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file based on `.env.example`:
```bash
cp .env.example .env
```

4. Update the `.env` file with your configuration:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/taskflow
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production
NODE_ENV=development
```

5. Start the backend server:
```bash
npm run dev
```

The backend will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file based on `.env.example`:
```bash
cp .env.example .env
```

4. Update the `.env` file:
```
VITE_API_URL=http://localhost:5000/api
```

5. Start the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173`

## Deployment

### Backend Deployment (Render/Railway)

1. **Prepare your repository**
   - Push your code to GitHub
   - Ensure `.env` is in `.gitignore`

2. **Deploy on Render**
   - Create a new Web Service
   - Connect your GitHub repository
   - Set the root directory to `backend`
   - Add environment variables in the dashboard
   - Deploy

3. **Deploy on Railway**
   - Create a new project
   - Connect your GitHub repository
   - Add environment variables
   - Railway will auto-detect and deploy

### Frontend Deployment (Vercel/Netlify)

1. **Deploy on Vercel**
   - Install Vercel CLI: `npm i -g vercel`
   - Navigate to frontend directory
   - Run: `vercel`
   - Add environment variable: `VITE_API_URL=your_backend_url`

2. **Deploy on Netlify**
   - Connect your GitHub repository
   - Set build command: `npm run build`
   - Set publish directory: `dist`
   - Add environment variable: `VITE_API_URL=your_backend_url`

### MongoDB Atlas Setup

1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Add a database user
4. Whitelist your IP (or use 0.0.0.0/0 for development)
5. Get your connection string
6. Update `MONGODB_URI` in your backend environment variables

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)

### Tasks
- `GET /api/tasks` - Get all user tasks (protected)
- `POST /api/tasks` - Create a new task (protected)
- `PUT /api/tasks/:id` - Update a task (protected)
- `DELETE /api/tasks/:id` - Delete a task (protected)

## Security Features

- Password hashing with bcrypt (10 salt rounds)
- JWT token authentication
- Protected API routes with middleware
- Input validation and sanitization
- CORS configuration
- Environment variable management
- HTTP-only cookie support (optional)

## Development

### Backend Development
```bash
cd backend
npm run dev  # Uses nodemon for auto-restart
```

### Frontend Development
```bash
cd frontend
npm run dev  # Vite dev server with HMR
```

## Building for Production

### Backend
```bash
cd backend
npm start
```

### Frontend
```bash
cd frontend
npm run build
npm run preview  # Preview production build
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Support

For issues and questions, please open an issue on GitHub.
# DekNek
