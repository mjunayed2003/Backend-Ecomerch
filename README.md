🛒 E-Commerce Backend (MERN + TypeScript)
Project Overview

This is a full-featured E-Commerce backend API built using Node.js, Express, MongoDB, and TypeScript.
It supports products, orders, users, payments (PayPal), and uploads with role-based access control (Admin/User).

The API handles user authentication, product management, order management, and payments efficiently and securely.

Features
Users

Register and login users

View and update user profiles

Admin can view, update, and delete users

Products

List all products or single product by ID

Admin can create, update, and delete products

Users can add product reviews

Top products retrieval

Orders

Users can create orders

View individual orders or all orders (Admin)

Update order payment status (PayPal integration)

Update delivery status (Admin only)

View logged-in user's orders

Payments

Fetch PayPal client ID for frontend integration

Uploads

Image upload handling using Multer

Only accepts images (.jpg, .jpeg, .png)

Installation

Clone the repository

git clone <your-repo-url>
cd ecomerch-backend


Install dependencies

npm install


Create a .env file:

MONGO_URI=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
PAYPAL_CLIENT_ID=<your-paypal-client-id>
PORT=5000


Start the server

npm run server


Start server + client concurrently (if frontend is in the same repo)

npm run dev

API Routes
Users
Method	Route	Description
POST	/api/users	Register user

POST	/api/users/login	User login

GET	/api/users/profile	Get logged-in user's profile

PUT	/api/users/profile	Update profile

GET	/api/users	Admin: get all users

GET	/api/users/:id	Admin: get user by ID

PUT	/api/users/:id	Admin: update user

DELETE	/api/users/:id	Admin: delete user
Products

Method	Route	Description

GET	/api/products	Get all products

GET	/api/products/top	Get top-rated products

GET	/api/products/:id	Get product by ID

POST	/api/products	Admin: create product

PUT	/api/products/:id	Admin: update product

DELETE	/api/products/:id	Admin: delete product

POST	/api/products/:id/reviews	Add product review
Orders

Method	Route	Description

POST	/api/orders	Create new order

GET	/api/orders	Admin: get all orders

GET	/api/orders/myorders	Get logged-in user's orders

GET	/api/orders/:id	Get order by ID

PUT	/api/orders/:id/pay	Update order to paid

PUT	/api/orders/:id/deliver	Admin: update order to delivered
Payments

Method	Route	Description

GET	/api/config/paypal	Fetch PayPal client ID
Uploads

Method	Route	Description
POST	/api/upload	Upload an image (jpg, jpeg, png only)

Built With

Node.js

Express.js

MongoDB

Mongoose

TypeScript

bcryptjs

jsonwebtoken

express-async-handler

Multer

Project Structure
backend/
├─ controllers/
│  ├─ orderController.ts
│  ├─ productController.ts
│  ├─ userController.ts
│  ├─ paypalController.ts
│  └─ uploadController.ts


├─ middleware/
│  └─ authMiddleware.ts


├─ models/
│  ├─ Order.ts
│  ├─ Product.ts
│  └─ User.ts


├─ routes/
│  ├─ orderRoutes.ts
│  ├─ productRoutes.ts
│  ├─ userRoutes.ts
│  ├─ paypalRoutes.ts
│  └─ uploadRoutes.ts


├─ utils/
│  └─ generateToken.ts
├─ server.ts
├─ tsconfig.json
└─ package.json
