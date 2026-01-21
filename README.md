# RatingStack - A Store Rating Platform

## Overview

Store Rating Platform is a full-stack web application designed to facilitate comprehensive store discovery and evaluation through a robust rating and review system. The platform enables users to discover, rate, and review retail establishments while providing store owners with powerful analytics tools to monitor performance metrics and customer sentiment. The architecture implements enterprise-grade authentication mechanisms, role-based access control, and real-time data synchronization across multiple user personas.

### Core Objectives

- Establish a scalable marketplace platform connecting consumers with retail establishments through transparent rating mechanisms
- Deliver role-based user experiences optimized for customers, store proprietors, and administrative personnel
- Implement advanced analytics capabilities for data-driven business intelligence
- Ensure data integrity and security through cryptographic authentication protocols and authorization frameworks

![Store Rating Platform](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)
![React](https://img.shields.io/badge/React-19.2.0-blue)
![NestJS](https://img.shields.io/badge/NestJS-10.0.0-red)
![TypeScript](https://img.shields.io/badge/TypeScript-5.1.3-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-8.11.0-blue)

## Deployment

### Backend Deployment
```bash
cd backend
npm run start:dev
```

### Frontend Deployment
```bash
cd frontend
npm start
# Deploy the 'build' folder to your hosting service
```

## Features

### Authentication & Authorization
- **Cryptographically Secure JWT-based Authentication** with refresh token rotation
- **Granular Role-Based Access Control (RBAC)** with three distinct user personas
- **Regular Users**: Consumer-facing capabilities for store discovery and rating submission
- **Store Owners**: Proprietor-level access with store management and performance analytics
- **Administrative Users**: System-wide management with full audit capabilities and cross-tenant analytics

### Store Management
- **Complete CRUD Operations** for retail establishment management
- **Advanced Analytics Dashboard** with aggregated rating statistics and performance metrics
- **Sophisticated Search & Filtering Infrastructure** with multi-parameter query capabilities
- **Responsive UI Components** leveraging modern CSS design patterns

### Rating System
- **Quantized Rating Mechanism** with five-tier evaluation scale and real-time feedback visualization
- **Live Rating Aggregation** with statistical calculations and persistent storage
- **Comprehensive Rating Audit Trail** maintaining temporal history of user evaluations
- **Idempotency Enforcement** preventing duplicate rating submissions

### Dashboard Analytics
- **Persona-Specific Dashboard Implementations** tailored to distinct user requirements
- **Interactive Data Visualization** with dynamic statistical charting
- **Real-time Data Synchronization** leveraging efficient WebSocket protocols
- **Data Export Infrastructure** enabling reporting and external data processing

### Modern UI/UX
- **Advanced Visual Design System** implementing glass-morphism patterns with CSS composition
- **Fluid Animation Framework** enabling smooth component transitions and micro-interactions
- **Mobile-First Responsive Architecture** ensuring cross-device compatibility
- **Comprehensive Accessibility Implementation** adhering to WCAG standards

## Tech Stack

### Backend Architecture
- **NestJS** - Opinionated, scalable Node.js framework with built-in dependency injection and modular architecture
- **TypeScript** - Statically-typed superset providing compile-time type safety and enhanced IDE support
- **PostgreSQL** - Enterprise-grade relational database management system with ACID compliance
- **TypeORM** - Object-relational mapping framework with advanced query builder and migration tools
- **JWT (JSON Web Tokens)** - Stateless authentication mechanism with cryptographic signing
- **Passport.js** - Comprehensive authentication middleware with pluggable strategies
- **bcrypt** - Industry-standard password hashing algorithm with adaptive work factors
- **class-validator** - Decorator-based data validation framework with comprehensive rule sets

### Frontend Technology Stack
- **React 19.2.0** - Modern UI library with concurrent rendering and hooks-based component architecture
- **TypeScript** - Static type checking with full IDE integration for enhanced developer experience
- **Tailwind CSS** - Utility-first CSS framework enabling rapid responsive design implementation
- **React Router v6** - Client-side routing with advanced path matching and lazy code splitting capabilities
- **Formik + Yup** - Form state management and schema-based validation orchestration
- **Axios** - Promise-based HTTP client with interceptor middleware for request/response transformation
- **Context API** - Built-in state management solution for cross-component communication without external dependencies

### Development & Tooling Infrastructure
- **ESLint** - Configurable static code analysis with pluggable rule sets for code quality enforcement
- **Prettier** - Opinionated code formatter ensuring consistent style across the codebase
- **Jest** - Comprehensive testing framework with snapshot testing and coverage reporting
- **PostCSS** - CSS transformation tool enabling next-generation CSS syntax compilation
- **Autoprefixer** - Automatic vendor prefix injection for cross-browser CSS compatibility

## Quick Start

### Prerequisites
- Node.js (v18 or higher) - Runtime environment with V8 JavaScript engine
- PostgreSQL (v12 or higher) - Relational database server with advanced indexing capabilities
- npm or yarn - Package management and dependency resolution tooling

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/store-rating-platform.git
cd store-rating-platform
```

### 2. Backend Setup
```bash
cd backend
npm install

# Create environment file
cp .env.example .env

# Update .env with your database credentials
# DATABASE_HOST=localhost
# DATABASE_PORT=5432
# DATABASE_USERNAME=postgres
# DATABASE_PASSWORD=your_password
# DATABASE_NAME=store_rating_db
# JWT_SECRET=your_jwt_secret_key

# Start the development server
npm run start:dev
```

### 3. Frontend Setup
```bash
cd frontend
npm install

# Start the development server
npm start
```

### 4. Database Setup
```sql
-- Create the database
CREATE DATABASE store_rating_db;

-- The application will automatically create tables on first run
```

## Project Structure

```
store-rating-platform/
├── backend/                 # NestJS backend microservice
│   ├── src/
│   │   ├── admin/          # Administrative module with RBAC
│   │   ├── auth/           # Authentication & authorization module
│   │   ├── config/         # Configuration management
│   │   ├── entities/       # TypeORM entity definitions
│   │   ├── stores/         # Store management business logic
│   │   └── users/          # User management and profile services
│   ├── dist/               # Compiled JavaScript output
│   └── package.json
├── frontend/               # React SPA application
│   ├── src/
│   │   ├── components/     # Reusable React components
│   │   ├── context/        # Context API state containers
│   │   ├── pages/          # Page-level route components
│   │   ├── services/       # API client services and utilities
│   │   └── types/          # TypeScript interface definitions
│   ├── public/             # Static asset serving directory
│   └── package.json
└── README.md
```

## Environment Variables

### Backend Configuration (.env)
```env
# PostgreSQL Connection Parameters
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USERNAME=postgres
DATABASE_PASSWORD=your_password
DATABASE_NAME=store_rating_db

# JWT Security Configuration
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRES_IN=24h

# Application Server Configuration
PORT=4000
NODE_ENV=development
```

### Frontend Configuration (.env)
```env
REACT_APP_API_URL=http://localhost:4000
REACT_APP_APP_NAME=Store Rating Platform
```

## 📚 API Documentation

### Authentication Endpoints
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `GET /auth/profile` - Get user profile

### Store Endpoints
- `GET /stores` - Get all stores
- `GET /stores/:id` - Get store by ID
- `POST /stores` - Create new store
- `PUT /stores/:id` - Update store
- `DELETE /stores/:id` - Delete store
- `POST /stores/:id/rate` - Rate a store
- `GET /stores/ratings/my` - Get user's ratings

### Admin Endpoints
- `GET /admin/users` - Get all users
- `POST /admin/users` - Create user
- `DELETE /admin/users/:id` - Delete user
- `GET /admin/stores` - Get all stores (admin view)
- `GET /admin/dashboard` - Get dashboard statistics

## User Roles & Permissions

### Regular User
- Retail establishment discovery and browsing
- Submission of quantized ratings to stores
- Access to personal rating evaluation history
- User profile administration and credential management

### Store Owner
- All capabilities of regular user persona
- Retail establishment CRUD operations
- Performance analytics and aggregated metrics visualization
- Store information and inventory management
- Resource deletion and lifecycle management

### Administrative User
- All capabilities of store owner persona
- System-wide user account management
- Cross-tenant store management and oversight
- Comprehensive system analytics and reporting
- Administrative dashboard with aggregated performance indicators




