# Authentication and SQL Joins Lab

A Node.js application demonstrating authentication and various types of SQL joins.

## Setup

1. Clone this repository
2. Install dependencies:
```bash
npm install
```
3. Create a `.env` file with required environment variables (see .env.example)
4. Start the server:
```bash
npm run dev
```

## SQL Joins Explained

This project demonstrates different types of SQL joins:

- **INNER JOIN**: Returns only the matching records from both tables
- **LEFT JOIN**: Returns all records from left table and matching records from right table
- **RIGHT JOIN**: Returns all records from right table and matching records from left table  
- **FULL OUTER JOIN**: Returns all records from both tables (implemented using UNION)
- **CROSS JOIN**: Returns cartesian product of both tables
- **SELF JOIN**: Joins a table to itself (useful for hierarchical/recursive relationships)

## API Endpoints

All report endpoints require authentication (Bearer token).

### Reports

| Endpoint | Description |
|----------|-------------|
| GET `/api/reports/users-with-roles` | Lists all users with their assigned roles using INNER JOIN |
| GET `/api/reports/users-with-profiles` | Shows users and their profiles (if any) using LEFT JOIN |
| GET `/api/reports/roles-right-join` | Lists roles and associated users using RIGHT JOIN |
| GET `/api/reports/profiles-full-outer` | Shows all users and profiles using FULL OUTER JOIN |
| GET `/api/reports/user-role-combos` | Displays all possible user-role combinations using CROSS JOIN |
| GET `/api/reports/referrals` | Shows user referral relationships using SELF JOIN |
| GET `/api/reports/latest-login` | Displays latest login information for each user |

### Authentication

| Endpoint | Description |
|----------|-------------|
| POST `/api/auth/signup` | Register a new user |
| POST `/api/auth/login` | Login and receive JWT token |
| POST `/api/auth/logout` | Revoke current JWT token |
| GET `/api/profile` | Get current user profile |

## Environment Variables

```
DB_HOST=localhost
DB_USER=root
DB_PASS=your_password
DB_NAME=lab_auth
DB_PORT=3306
SERVER_PORT=3000
JWT_SECRET=your_secret_key
JWT_EXPIRES=1h
```

## Dependencies

- express: Web framework
- mysql2: MySQL client
- jsonwebtoken: JWT authentication
- bcryptjs: Password hashing
- cors: Cross-origin resource sharing
- dotenv: Environment variables
- uuid: Generate unique IDs

## Development

```bash
npm run dev
```

Runs the server in development mode with nodemon for auto-reloading.
