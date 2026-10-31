# Fullstack-Book-E-Commerce-Platform
    Ecomica is a full-stack online bookstore developed using React and TypeScript for the frontend, with Java Spring Boot and MongoDB powering the backend. It provides a role-based shopping environment for buyers, sellers, and administrators, featuring an Amazon-inspired interface, JWT-based authentication, book management, secure checkout, and order processing.

Features
1. Buyer Features
    - Buyer registration and login.
    - Browse and discover books using search, categories, and filters such as price range, stock availability, format, and language.
    - View detailed book information, including ISBN, publisher, publication year, language, and format.
    - Discover related books and frequently purchased titles.
    - Ask questions about books and view answers provided by sellers or administrators.
    - Submit book reviews with verified-purchase badges for eligible buyers.
    - Add, remove, and manage shopping cart items and quantities.
    - Maintain a personal wishlist.
    - Add, edit, and manage delivery addresses.
    - Manage buyer profiles, account information, and loyalty points.
    - Save and manage payment options, including Card and UPI.
    - Complete purchases through a multi-step checkout process: Address → Payment → Review.
    - Apply promotional discount codes during checkout.
    - View order history, order details, coupon information, and price breakdowns.
    - Cancel orders with PLACED status.
    - Track order progress through status timelines.

2. Seller Features
    - Seller registration and login.
    - Dedicated seller dashboard with a separate visual theme.
    - Create and delete personal book listings.
    - Add book information, including category, ISBN, language, format, publisher, and publication year.
    - View orders containing their listed books with read-only order information.
    - Manage seller profiles and store account details.
    - Save and manage payment methods, including Card and UPI.
    - Access seller analytics, including:
      - Total number of listed books.
      - Total units sold.
      - Overall sales revenue.
      - Best-selling books.
      - Low-stock notifications.

3. Admin Features
      - Secure administrator login.
      - Dedicated admin dashboard with overall platform statistics.
      - Monitor total registered users, orders, revenue, and pending book approvals.
      - Review and moderate book listings through Approve, Reject, and Reset actions.
      - Block and unblock user accounts.
      - Search and filter book moderation records.
      - Load additional moderation records using pagination.

 4. User Interface and Experience Enhancements
      - Amazon-inspired homepage and product presentation.
      - Interactive hero slider with navigation controls.
      - Product cards with links to relevant filtered book listings.
      - Role-based navigation and protected routes.
      - Automatic redirection to the appropriate page after login.
      - Animated toast notifications for application feedback.
      - Smooth page transitions with reduced-motion accessibility support.
      - Improved seller dashboard with listing status indicators and reload functionality.
      - Vite proxy configuration for reliable communication between frontend and backend APIs.
   
 5.Checkout and Pricing Rules
      - Standard shipping fee of Rs. 49.
      - Free shipping when the merchandise amount after discounts reaches Rs. 999 or above.
      - 5% tax calculated on the discounted merchandise amount.
      - Promotional coupon support:
        - SAVE10 – 10% discount.
        - WELCOME15 – 15% discount for purchases with a minimum merchandise value of Rs. 500.
      - Checkout displays merchandise price, discounts, shipping charges, tax, and final payable amount consistently with backend calculations.

Technology Stack
  Frontend
      - React
      - TypeScript
      - Vite
      - React Router
      - Axios
      - Custom CSS

  Backend
      - Java 21
      - Spring Boot 3
      - Spring Security
      - JWT Authentication
      - Spring Data MongoDB
      - Maven
      
  Database
      - MongoDB (local or cloud deployment)

  Prerequisites
      - Node.js 18 or later
      - npm
      - Java 21
      - Maven 3.9 or later
      - MongoDB (local installation or cloud database)
      
  Environment Configuration
    Backend configuration files:
        - backend/src/main/resources/application.properties
        - backend/src/main/resources/application-prod.properties  

  The application supports the following environment properties:
    Purpose	Configuration
          MongoDB connection:	spring.data.mongodb.uri or MONGO_URI
          JWT secret key:	app.jwt.secret or JWT_SECRET
          JWT expiration:	app.jwt.expiration-ms
          Demo data initialization:	app.seed.enabled
          Admin email:	ADMIN_EMAIL
          Admin password:	ADMIN_PASSWORD

  Example local configuration:
          spring.data.mongodb.uri=mongodb://localhost:27017/ecomica3
          app.jwt.secret=change-me-to-a-long-random-secret-at-least-32-chars
          app.jwt.expiration-ms=86400000
          app.seed.enabled=true

  For production deployment, activate the prod profile, configure a strong JWT secret, and disable demo data initialization.

  Running the Project Locally
      1. Start the Backend
            cd backend
            mvn spring-boot:run


  Backend URL: http://localhost:8080

      2. Start the Frontend
              cd frontend
              npm install
              npm run dev

  Frontend URL: http://localhost:5173

  If port 5173 is occupied, Vite automatically selects another available port. If backend port 8080 is already in use, stop the existing Java/Spring process or configure a different server port.
Development Networking
    - Frontend communicates with backend services through the relative /api endpoint.
    - Vite proxy settings are configured in frontend/vite.config.ts.
    - API requests are forwarded to http://127.0.0.1:8080.
    - Restart the frontend development server whenever the Vite proxy configuration is modified.

  Demo Login Credentials
  Role, email and Password
    Role	 :
      01.  Buyer  :     buyer2@ecomica.com  :  buyer234
      02.  Seller :     seller2@ecomica.com :  seller234
      03.  Admin  :   	admin@ecomica.com	  :  admin123


  Main Frontend Routes
    Route AND Purpose

  /	: Homepage
  /login	:             User login
  /register	:           User registration
  /buyer/dashboard:   Buyer dashboard
  /buyer/profile:       Buyer profile
  /buyer/book/:id:	    Book details
  /buyer/cart	:         Shopping cart
  /buyer/orders:	      Order history
  /seller/dashboard :	  Seller dashboard
  /seller/profile	:     Seller profile
  /admin/dashboard :	  Admin dashboard

Backend API Endpoints
  API Group	Functionality
  /api/auth/*	:              User authentication and registration
  /api/books/*	:            Book catalogue, filtering, and management
  /api/categories/* :	       Book categories
  /api/cart/*	:              Shopping cart operations
  /api/orders/*	:            Checkout and order management
  /api/reviews/*	:          Book reviews
  /api/wishlist/*	:          Wishlist management
  /api/addresses/*	:        Delivery address management
  /api/profile/*	:          User profile and loyalty points
  /api/payment-methods/*	:  Saved payment methods
  /api/seller/*	:            Seller listings, analytics, and orders
  /api/admin/*	:            Administrative user, order, and book moderation
    
    	     

   

    
                        
