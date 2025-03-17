# Payslip Management System

A full-stack payslip management application built with React, Node.js, Express, and MongoDB.

## Features

- 🔐 User authentication and role-based access control
- 👥 Employee management
- 💰 Payslip generation and processing
- 📊 Dashboard with key metrics
- 📄 PDF generation for payslips
- 🔍 Search and filtering capabilities
- 📱 Responsive design for all devices

## Tech Stack

### Frontend
- React.js
- React Router for navigation
- Axios for API requests
- CSS for styling

### Backend
- Node.js
- Express.js for API development
- MongoDB for database
- Mongoose as ODM
- JWT for authentication
- PDFKit for generating PDF payslips

### DevOps
- Docker for containerization
- Docker Compose for multi-container orchestration

## Architecture

The application follows a microservices architecture with three main components:

1. **Frontend Container**: React application served by Nginx
2. **Backend Container**: Node.js Express API
3. **Database Container**: MongoDB

## Project Structure

```
payslip-app/
├── docker-compose.yml
├── .env
├── frontend/
│   ├── Dockerfile
│   ├── src/
│   │   ├── components/
│   │   ├── services/
│   │   └── styles/
├── backend/
│   ├── Dockerfile
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   └── utils/
└── mongodb/
```

## Getting Started

### Prerequisites

- Docker and Docker Compose
- Node.js and npm (for local development)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ajeetraina/payslip-management-system.git
   cd payslip-management-system
   ```

2. Create a `.env` file in the root directory with the following variables:
   ```
   MONGO_URI=mongodb://mongodb:27017/payslip-app
   JWT_SECRET=your_jwt_secret_key_change_in_production
   ```

3. Build and run the application using Docker Compose:
   ```bash
   docker-compose up -d
   ```

4. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

### Local Development

For local development without Docker:

1. Install dependencies for the backend:
   ```bash
   cd backend
   npm install
   ```

2. Install dependencies for the frontend:
   ```bash
   cd frontend
   npm install
   ```

3. Start the backend server:
   ```bash
   cd backend
   npm start
   ```

4. Start the frontend development server:
   ```bash
   cd frontend
   npm start
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Employees
- `GET /api/employees` - Get all employees
- `GET /api/employees/:id` - Get single employee
- `POST /api/employees` - Create new employee
- `PUT /api/employees/:id` - Update employee
- `DELETE /api/employees/:id` - Delete employee

### Payslips
- `GET /api/payslips` - Get all payslips
- `GET /api/payslips/employee/:employeeId` - Get payslips by employee
- `GET /api/payslips/:id` - Get single payslip
- `POST /api/payslips` - Create new payslip
- `POST /api/payslips/:id/generate` - Generate PDF payslip
- `PATCH /api/payslips/:id/status` - Update payslip status

## User Roles and Permissions

- **Admin**: Full access to all features
- **HR**: Can manage employees and payslips
- **Accountant**: Can create and manage payslips
- **Manager**: Can view all employees and payslips

## License

This project is licensed under the MIT License - see the LICENSE file for details.