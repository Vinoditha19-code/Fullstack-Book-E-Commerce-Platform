# 📚 Ecomica – Full-Stack Book E-Commerce Platform

Ecomica is a full-stack online bookstore developed using **React and TypeScript** for the frontend, with **Java Spring Boot and MongoDB** powering the backend. It provides a role-based shopping environment for buyers, sellers, and administrators, featuring an Amazon-inspired interface, JWT-based authentication, book management, secure checkout, and order processing.

## ✨ Features

### 1. Buyer Features
- Buyer registration and login.
- Browse and discover books using search, categories, and filters:
  - Price range
  - Stock availability
  - Book format
  - Language
- View detailed book information, including ISBN, publisher, publication year, language, and format.
- Discover related books and frequently purchased titles.
- Ask questions about books and view answers from sellers or administrators.
- Submit book reviews with verified-purchase badges for eligible buyers.
- Add, remove, and manage shopping cart items and quantities.
- Create and manage personal wishlists.
- Add, edit, and manage delivery addresses.
- Manage buyer profiles, account information, and loyalty points.
- Save and manage payment methods (Card and UPI).
- Complete purchases through a multi-step checkout process:
  - Address
  - Payment
  - Order Review
- Apply promotional discount coupons during checkout.
- View order history, order details, coupon information, and price breakdowns.
- Cancel orders with `PLACED` status.
- Track order progress through status timelines.

### 2. Seller Features
- Seller registration and login.
- Dedicated seller dashboard with a separate visual theme.
- Create and delete personal book listings.
- Add book details, including:
  - Category
  - ISBN
  - Language
  - Format
  - Publisher
  - Publication year
- View orders containing their listed books with read-only order information.
- Manage seller profiles and store account details.
- Save and manage payment methods (Card and UPI).
- Access seller analytics, including:
  - Total number of listed books.
  - Total units sold.
  - Overall sales revenue.
  - Best-selling books.
  - Low-stock notifications.

### 3. Admin Features
- Secure administrator login.
- Dedicated admin dashboard with overall platform statistics.
- Monitor:
  - Total registered users.
  - Total orders.
  - Overall revenue.
  - Pending book approvals.
- Review and moderate book listings using:
  - Approve
  - Reject
  - Reset
- Block and unblock user accounts.
- Search and filter book moderation records.
- Load additional moderation records using pagination.

### 4. User Interface and Experience
- Amazon-inspired homepage and product presentation.
- Interactive hero slider with navigation controls.
- Product cards with links to relevant filtered book listings.
- Role-based navigation and protected routes.
- Automatic redirection to the appropriate page after login.
- Animated toast notifications for application feedback.
- Smooth page transitions with reduced-motion accessibility support.
- Seller dashboard with listing status indicators and reload functionality.
- Vite proxy configuration for reliable frontend-backend communication.

### 5. Checkout and Pricing Rules
- **Standard Shipping:** Rs. 49.
- **Free Shipping:** Applied when the merchandise amount after discounts reaches Rs. 999 or above.
- **Tax:** 5% calculated on the discounted merchandise amount.

**Promotional Coupons:**

| Coupon Code | Discount | Condition |
|---|---:|---|
| `SAVE10` | 10% | No minimum purchase specified |
| `WELCOME15` | 15% | Minimum merchandise value of Rs. 500 |

**Checkout Price Breakdown:**
- Merchandise price.
- Promotional discounts.
- Shipping charges.
- Applicable tax.
- Final payable amount.

The checkout displays pricing consistently with backend calculations.

---

## 🛠️ Technology Stack

### Frontend
- React
- TypeScript
- Vite
- React Router
- Axios
- Custom CSS

### Backend
- Java 21
- Spring Boot 3
- Spring Security
- JWT Authentication
- Spring Data MongoDB
- Maven

### Database
- MongoDB (Local or Cloud Deployment)

---

## 📋 Prerequisites

Make sure the following software is installed before running the project:

- Node.js 18 or later
- npm
- Java 21
- Maven 3.9 or later
- MongoDB (Local installation or Cloud database)

---

## ⚙️ Environment Configuration

### Backend Configuration Files

- `backend/src/main/resources/application.properties`
- `backend/src/main/resources/application-prod.properties`

### Supported Environment Properties

| Purpose | Configuration |
|---|---|
| MongoDB Connection | `spring.data.mongodb.uri` or `MONGO_URI` |
| JWT Secret Key | `app.jwt.secret` or `JWT_SECRET` |
| JWT Expiration | `app.jwt.expiration-ms` |
| Demo Data Initialization | `app.seed.enabled` |
| Admin Email | `ADMIN_EMAIL` |
| Admin Password | `ADMIN_PASSWORD` |

### Example Local Configuration

```properties
spring.data.mongodb.uri=mongodb://localhost:27017/ecomica3
app.jwt.secret=change-me-to-a-long-random-secret-at-least-32-chars
app.jwt.expiration-ms=86400000
app.seed.enabled=true
```

**Production Configuration:**
- Activate the production profile.
- Configure a strong JWT secret.
- Disable demo data initialization.
- Use appropriate production database credentials.

---

## 🚀 Running the Project Locally

### Step 1: Start the Backend

Open a terminal and execute:

```bash
cd backend
mvn spring-boot:run
```

Backend URL:

`http://localhost:8080`

### Step 2: Start the Frontend

Open another terminal and execute:

```bash
cd frontend
npm install
npm run dev
```

Frontend URL:

`http://localhost:5173`

**Note:** If port `5173` is occupied, Vite automatically selects another available port. If backend port `8080` is already in use, stop the existing Java/Spring process or configure a different server port.

---

## 🌐 Development Networking

- The frontend communicates with backend services through the relative `/api` endpoint.
- Vite proxy settings are configured in `frontend/vite.config.ts`.
- API requests are forwarded to `http://127.0.0.1:8080`.
- Restart the frontend development server whenever the Vite proxy configuration is modified.

---

## 🔑 Demo Login Credentials

Use the following credentials to explore the different user roles:

| Role | Email | Password |
|---|---|---|
| Buyer | `buyer2@ecomica.com` | `buyer234` |
| Seller | `seller2@ecomica.com` | `seller234` |
| Admin | `admin@ecomica.com` | `admin123` |

---

## 🧭 Main Frontend Routes

| Route | Purpose |
|---|---|
| `/` | Homepage |
| `/login` | User Login |
| `/register` | User Registration |
| `/buyer/dashboard` | Buyer Dashboard |
| `/buyer/profile` | Buyer Profile |
| `/buyer/book/:id` | Book Details |
| `/buyer/cart` | Shopping Cart |
| `/buyer/orders` | Order History |
| `/seller/dashboard` | Seller Dashboard |
| `/seller/profile` | Seller Profile |
| `/admin/dashboard` | Admin Dashboard |

---

## 🔌 Backend API Endpoints

| API Endpoint | Functionality |
|---|---|
| `/api/auth/*` | User Authentication and Registration |
| `/api/books/*` | Book Catalogue, Filtering, and Management |
| `/api/categories/*` | Book Categories |
| `/api/cart/*` | Shopping Cart Operations |
| `/api/orders/*` | Checkout and Order Management |
| `/api/reviews/*` | Book Reviews |
| `/api/wishlist/*` | Wishlist Management |
| `/api/addresses/*` | Delivery Address Management |
| `/api/profile/*` | User Profile and Loyalty Points |
| `/api/payment-methods/*` | Saved Payment Methods |
| `/api/seller/*` | Seller Listings, Analytics, and Orders |
| `/api/admin/*` | Administrative User, Order, and Book Moderation |

---

## 🔒 Important Implementation Details

- Demo data is automatically initialized during local development when seeding is enabled.
- Demo data initialization is disabled by default under the production profile.
- Only approved and active books are displayed in the public catalogue.
- Newly submitted seller listings remain pending until administrator approval.
- Blocked accounts are prevented from logging in.
- JWT authentication provides secure login sessions and role-based access control.
- The JWT filter handles invalid or expired tokens gracefully to avoid interfering with the login process.

---

## 👥 User Roles

Ecomica supports three main user roles:

- **Buyer:** Browse books, manage shopping carts, place orders, and track purchases.
- **Seller:** Manage book listings, view sales analytics, and monitor orders.
- **Admin:** Manage users, monitor platform statistics, and moderate book listings.

---

## 📌 Project Highlights

- Full-stack application development.
- Role-based authentication and authorization.
- RESTful API integration.
- MongoDB database management.
- Shopping cart and order processing.
- Multi-step checkout and coupon management.
- Separate dashboards for buyers, sellers, and administrators.
- Responsive and interactive user interface.
