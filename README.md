# HCMUS-WebAppDev

## Table of Contents

- [Description](#description)
- [Features](#features)
  - [Main System](#main-system)
  - [Auxiliary System (Payment Management)](#auxiliary-system-payment-management)
  - [Connecting the Management and Payment Systems](#connecting-the-management-and-payment-systems)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Setup and Running the Project](#setup-and-running-the-project)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Usage](#usage)
  - [Interfaces](#interfaces)

## Description

HCMUS-WebAppDev is a web application developed for the Web Application Development course. It consists of two systems: the **Main System** (a management application) and the **Auxiliary System** (Payment Management). The project follows the **MVC architecture**, integrates **AJAX** for dynamic updates, and uses **Express.js** for server-side operations. It implements **authentication and role-based authorization** for security.

## Features

### Main System

- **Management Application**: Supports shopping cart, payment processing, statistics, and CRUD operations.
- **Authentication and Authorization**: Implements role-based authentication for at least two types of users (Client and Admin).
- **User Interfaces**: Provides separate interfaces for Clients (users) and Admins (system administrators).
- **MVC Architecture**: Organizes the application using the Model-View-Controller pattern.
- **AJAX Integration**: Enhances interactivity through asynchronous requests.
- **Backend**: Built with Node.js and Express.js.
- **Database**: Utilizes MongoDB with meaningful and complete datasets.

### Auxiliary System (Payment Management)

- **System Initialization**: Begins with a main account to receive payments from users.
- **User Accounts**: Each user has an account in the auxiliary system containing an ID and a balance.
- **Payment Transactions**: Supports money transfers from user accounts to the main account.
- **Account Management**: Allows automatic account creation when a new user is registered in the main system.
- **Payment Reconciliation**: Implements a reconciliation mechanism for payment transactions.

### Connecting the Management and Payment Systems

- **WebAPI Communication**: The two systems communicate through WebAPI.
- **Authentication and Security**: Ensures a secure process for handling transactions.

## Project Structure

```
HCMUS-WebAppDev/
├── main/
|   ├── config/            # Configuration files, including database configuration
|   |   └── db.config.js
│   ├── controllers/       # Controllers for handling requests and business logic
|   ├── helpers/           # Helper functions and utilities
│   ├── models/            # Database models
│   ├── routes/            # Route definitions
|   ├── source/            # Source files for the application
|   |   ├── public/        # Public assets (CSS, JS, images)
|   |   ├── resources/     # Resources for the application
|   |   |   ├── scss/      # SCSS files for styling
|   |   |   └── views/     # View templates
|   |   ├── app.js         # Main application file
|   |   └── server.js      # Server setup and configuration
│   └── utils/             # Utility functions
|       └── mongoose.js    # Mongoose configuration and connection
├── auxiliary/
|   ├── cert/              # Certificates for secure communication
|   ├── config/            # Configuration files, including database configuration
|   |   └── db.config.js
│   ├── controllers/       # Controllers for handling requests and business logic
|   ├── helpers/           # Helper functions and utilities
│   ├── models/            # Database models
│   ├── routes/            # Route definitions
│   └── source/            # Source files for the application
|       ├── public/        # Public assets (CSS, JS, images)
|       ├── resources/     # Resources for the application
|       |   ├── scss/      # SCSS files for styling
|       |   └── views/     # View templates
|       ├── app.js         # Main application file
|       └── server.js      # Server setup and configuration
├── README.md              # Project documentation
├── package.json           # Project dependencies and scripts
└── .env                   # Environment variables

```

## Technologies Used

- **Frontend**: HTML, CSS, JavaScript, Handlebars.js for templating
- **Backend**:Node.js, Express.js, Mongoose for MongoDB
- **Authentication & Security**: Passport.js, JWT, bcrypt for password hashing, express-session, Redis for session management
- **Additional Libraries**: Axios for API requests, Nodemailer for email notifications

## Setup and Running the Project

### Prerequisites

- Node.js
- npm (Node Package Manager)
- MongoDB

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/lpchi133/HCMUS-WebAppDev.git
   cd HCMUS-WebAppDev
   ```

2. Install dependencies for both systems:

   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file and configure the following variables:

   ```env
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   GOOGLE_CALLBACK_URL=your_google_callback_url
   URL_GG=https://accounts.google.com/o/oauth2/v2/auth
   HOST=127.0.0.1
   MAIN_PORT=3000
   AUX_PORT=1234
   AS_DATABASE=your_database_connection_string_for_auxiliary_system  MS_DATABASE=your_database_connection_string_for_main_system
   JWT_ACCESS_KEY=your_jwt_secret
   ```

4. Set up the database:
   - Ensure MongoDB is running.
   - Configure the database connection in the configuration files.

### Running the Application

1. Start both systems simultaneously:
   ```bash
   npm run start
   ```
2. Watch for changes in SCSS files:

   ```bash
   npm run watch
   ```

3. Access the application:
   - **Main System**: `http://localhost:3000`
   - **Auxiliary System**: `https://localhost:1234`

> **Note:** If you encounter issues with the interface not loading CSS properly, navigate to `source/scss/app.scss` and press **Ctrl + S** to save the file. This should trigger the necessary updates to compile and load the CSS.

## Usage

- **Client Interface:** Clients can browse and purchase items using the client interface.
- **Admin Interface:** Admins manage users, products, and view statistics via the admin interface.
  - **Admin Account:** Use the following credentials to log in as an admin:
    - **Email:** mozi.ecommerce@gmail.com
    - **Password:** 123456
- **Payment Management:** The auxiliary system handles user payments and transaction reconciliation.

### Interfaces

**Client Interface:**

- Login page
  ![Login page](docs/imgs/login_page.jpeg)

- Homepage
  ![Hompage](docs/imgs/homepage.jpeg)

- Shopping page
  ![Shopping page](docs/imgs/shopping.jpeg)

- Product Detail
  ![Product Detail](docs/imgs/product_detail.jpeg)

- Checkout Page
  ![Checkout page](docs/imgs/checkout.jpeg)
  ![inf](docs/imgs/inf_payment.jpeg)
  ![verify page](docs/imgs/verify.jpeg)
  ![Payment successful](docs/imgs/payment_success.jpeg)

- Account settings
  ![acc settings](docs/imgs/account_settings.jpeg)

- Order history
  ![Order history](docs/imgs/orders_history.jpeg)

**Admin Interface:**

- Dashboard
  ![Dashboard](docs/imgs/dashboard.jpeg)

- Manage Products
  ![Manage Product](docs/imgs/manage_product.png)
  ![Edit Product](docs/imgs/edit_product.png)
- Add Product
  ![Add  Product](docs/imgs/add_product.png)
- Manage Users
  ![Manage Users](docs/imgs/manage_users.png)
  ![Edit user](docs/imgs/edit_user.png)

- Manage Categories
  ![Manage Categories](docs/imgs/manage_categories.jpeg)
  ![Edit Category](docs/imgs/edit_category.jpeg)

- Manage orders
  ![Manage orders](docs/imgs/manage_orders.png)
  ![Manage orders](docs/imgs/manage_orders2.png)

**Auxiliary System Interface:**
![Auxiliary System](docs/imgs/auxiliar_system.jpeg)
