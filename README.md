🛒 Backend-Ecomerch

A Production-Ready E-Commerce Backend built with Express, TypeScript, MongoDB 

This repository contains the complete backend system for an E-Commerce platform including authentication, orders, product management, reviews, and admin controls.

🚀 Features
🔐 Authentication & Users

User Registration & Login

JWT-based Authentication

Admin Role Protection

User Profile & Update

Password Hashing (bcrypt)

🛍 Products

Create, Update, Delete Products

Get All Products / Single Product

Product Search & Filters

Product Reviews (with rating)

📦 Orders

Create Orders

Update Order Status

Payment Status

Get User Orders

Admin – Get All Orders


🧪 Unit Tests Included

Controllers, Routes & Utilities tested with:

Jest

Supertest

📁 Project Structure
Backend-Ecomerch/
│── controllers/
│   ├── orderController.ts
│   ├── paypalController.ts
│   ├── productController.ts
│   └── userController.ts



│── data/
│   ├── orderController.test.ts
│   ├── paypalController.test.ts
│   ├── productController.test.ts
│   ├── userController.test.ts
│   ├── orders.test.ts
│   ├── products.test.ts
│   ├── reviews.test.ts
│   └── users.test.ts


│── middlewares/
│   ├── authMiddleware.ts
│   ├── authMiddleware.test.ts
│   └── errorMiddleware.ts


│── models/
│   ├── userModel.ts
│   ├── productModel.ts
│   ├── orderModel.ts
│   └── index.ts


│── routes/
│   ├── orderRoutes.ts
│   ├── paypalRoutes.ts
│   ├── productRoutes.ts
│   ├── uploadRoutes.ts
│   └── userRoutes.ts



│── utils/
│   ├── generateToken.ts
│   └── generateToken.test.ts
│── server.ts
│── seeder.ts
│── package.json
│── tsconfig.json
└── .gitignore

📦 Installation
npm install

⚙️ Environment Setup

Create a .env file:

PORT=5000
MONGO_URI=your_mongodb_url
JWT_SECRET=your_secret_key
NODE_ENV=development

optional papal
PAYPAL_CLIENT_ID=your_client_id
PAYPAL_SECRET=your_secret_key
PAYPAL_API_URL=https://api-m.sandbox.paypal.com

▶️ Running the Server
Development
npm run dev

Production Build
npm run build
npm start

🧪 Running Tests

Run all tests:

npm test


Run individual test:

npm test -- productController.test.ts

🚀 API Endpoints
👤 Users

POST /api/users/register
POST /api/users/login
GET /api/users/profile
PUT /api/users/profile

🛒 Products

GET /api/products
GET /api/products/:id
POST /api/products (admin)
PUT /api/products/:id (admin)
DELETE /api/products/:id (admin)
POST /api/products/:id/reviews

📦 Orders

POST /api/orders
GET /api/orders/myorders
GET /api/orders (admin)
PUT /api/orders/:id/pay
PUT /api/orders/:id/deliver (admin)

💳 PayPal

POST /api/paypal/create-order
POST /api/paypal/capture-order

🛠 Scripts
"scripts": {
  "dev": "ts-node-dev --respawn --transpile-only server.ts",
  "build": "tsc",
  "start": "node dist/server.js",
  "test": "jest"
}

🧹 Code Quality

TypeScript Strict Mode

Centralized Error Handling

Reusable Middleware

Clean & Modular Architecture
