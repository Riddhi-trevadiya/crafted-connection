# Crafted Connections 🪑

A furniture and home decor e-commerce web application where users can explore products, create accounts, manage a shopping cart, and place orders.

## Overview

Crafted Connections is a full-stack e-commerce project built to explore the development of an online furniture shopping experience. It combines a responsive frontend with a Node.js and Express backend, REST API endpoints, user authentication, and SQLite database integration.

## Features

### User Authentication
- User registration and login
- Password hashing using bcrypt
- JWT-based authentication
- Persistent login using stored authentication tokens
- Protected API endpoints

### Product Management
- Browse furniture and home decor products
- Product information including price, category, rating, and stock
- Add products through an authenticated API endpoint
- Preloaded sample product catalogue

### Shopping Cart
- Add products to cart
- Increase and decrease item quantities
- Remove items from cart
- View cart totals
- Persist cart data using browser local storage

### Order Management
- Submit orders through an authenticated API
- Store order and order-item information
- Associate orders with registered users

### Additional Pages
- Home
- About
- Products
- Categories
- Contact
- Add Product

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | Node.js, Express.js |
| Database | SQLite |
| ORM | Sequelize |
| Authentication | JSON Web Tokens (JWT) |
| Password Security | bcryptjs |
| Configuration | dotenv |

## Project Structure

```text
crafted-connection/
│
├── index.html
├── about.html
├── product.html
├── categories.html
├── contact.html
├── add-product.html
│
├── new.css
├── new.js
│
├── server.js
├── seed.js
│
├── package.json
├── package-lock.json
├── .gitignore
└── .env.example
```

## Getting Started

### Prerequisites

- Node.js
- npm
- Git

### 1. Clone the repository

```bash
git clone https://github.com/Riddhi-trevadiya/crafted-connection.git
cd crafted-connection
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a local `.env` file in the project root.

```env
PORT=3000
JWT_SECRET=your_generated_secret
```

Generate a secure JWT secret and never commit your `.env` file.

### 4. Start the application

```bash
npm start
```

The application runs at:

```text
http://localhost:3000
```

Health check:

```text
http://localhost:3000/api/health
```

### 5. Seed sample products (optional)

```bash
npm run seed
```

**Warning:** The seed script uses `sequelize.sync({ force: true })`, which drops and recreates existing database tables. Run it only when you are comfortable resetting the local database.

## API Endpoints

| Method | Endpoint | Description | Authentication |
|---|---|---|---|
| POST | `/api/auth/register` | Register a user | No |
| POST | `/api/auth/login` | Log in a user | No |
| GET | `/api/auth/me` | Retrieve current user details | Yes |
| GET | `/api/products` | Retrieve products | No |
| POST | `/api/products` | Add a product | Yes |
| POST | `/api/orders` | Place an order | Yes |
| GET | `/api/health` | Check server health | No |

Protected endpoints require a JWT in the Authorization header:

```text
Authorization: Bearer <token>
```

## Database Models

The application uses Sequelize models for:

- **User:** Name, email, and hashed password
- **Product:** Name, description, price, category, image, rating, and stock
- **Order:** User association, total amount, and order status
- **OrderItem:** Product association, quantity, and price

## Learning Outcomes

This project provided practical experience with:

- Building REST APIs using Express.js
- Implementing JWT authentication
- Hashing passwords securely
- Designing relational data models and associations
- Integrating SQLite with Sequelize
- Connecting frontend JavaScript to backend APIs
- Managing client-side cart state with local storage

## Future Improvements

- Product search, filtering, and sorting
- Improved product and inventory management
- Order history and order tracking
- Payment gateway integration
- Input validation and centralized error handling
- Automated backend testing
- Deployment and production configuration

---

**Crafted Connections** — A full-stack learning project focused on furniture and home decor e-commerce.
