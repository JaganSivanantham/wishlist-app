Wishlist Application
A full-stack web application for users to create, manage, and share their personal wishlists.

Table of Contents

About the Project
Features
Technologies Used
Getting Started
Prerequisites
Backend Setup
Frontend Setup
Deployment
Usage
Project Structure
Contributing
License
Contact

About The Project
This project is a personal wishlist management application built as a full-stack solution. 
It allows users to register accounts, log in securely, create multiple wishlists, and add/remove items to them. T
he backend provides a RESTful API, while the frontend is a responsive single-page application (SPA).

Features

User Authentication: Secure registration and login functionalities.
Passwords are encrypted using BCrypt for security.
Wishlist Management: Create, view, update, and delete individual wishlists.
Item Management: Add, edit, and remove items within each wishlist.
User Profiles: (Basic) View user information.
Responsive Design: (If applicable) User interface adapts to various screen sizes.

Technologies Used

The project is divided into two main parts:
Backend
Java 17+
Spring Boot 3+: Framework for building the REST API.
Spring Data MongoDB: For interacting with the MongoDB database.
MongoDB Atlas: Cloud-hosted NoSQL database.
Maven: Dependency management and build automation.
BCrypt: For secure password hashing.
Lombok: To reduce boilerplate code.

Frontend

React.js: JavaScript library for building user interfaces.
Axios: Promise-based HTTP client for API requests.
React Router DOM: For client-side routing.
JavaScript (ES6+)
HTML5 & CSS3

Getting Started

Follow these instructions to set up the project locally on your machine.

Prerequisites

Make sure you have the following installed:
Java Development Kit (JDK) 17 or higher
Maven 3.6.0 or higher
Node.js 14.x or higher
npm 6.x or higher (or Yarn)
Git
MongoDB Atlas Account: For your database.

Backend Setup
Clone the repository:


Configure MongoDB Connection:

Create an account on MongoDB Atlas.
Create a new cluster.
Go to "Database Access" and add a new database user.
Go to "Network Access" and add your current IP address or allow access from anywhere (for development, but restrict for production).
Go to "Databases" -> "Connect" -> "Connect your application" and copy the connection string (e.g., mongodb+srv://<username>:<password>@cluster0.abcde.mongodb.net/).
Create or modify src/main/resources/application.properties in your wishlist-backend directory and add your MongoDB URI:



spring.data.mongodb.uri=[YOUR_MONGODB_ATLAS_CONNECTION_STRING_HERE]
# Example: spring.data.mongodb.uri=mongodb+srv://youruser:yourpassword@cluster0.abcde.mongodb.net/wishlistdb?retryWrites=true&w=majority
Important: Replace <username>, <password>, and cluster0.abcde.mongodb.net with your actual MongoDB Atlas credentials and cluster URL. 
Make sure to include your database name (e.g., wishlistdb) in the connection string if you want to explicitly name it.

Build and Run the Backend:

Bash
mvn clean install
mvn spring-boot:run
The backend should start on http://localhost:8080 (or your configured port).

Frontend Setup
Navigate to the frontend directory:

Bash
cd ../wishlist-frontend # If you are still in wishlist-backend
# or if you are at the root of the cloned repo:
# cd wishlist-frontend

Install dependencies:

Bash
npm install
# or
yarn install

Configure API Base URL:

Create a .env file in the root of your wishlist-frontend directory.

Add your backend's URL:
Code snippet

REACT_APP_API_BASE_URL=http://localhost:8080/api
# For Render deployment: REACT_APP_API_BASE_URL=https://your-render-app-url.onrender.com/api
Run the Frontend Development Server:

Bash

npm start
# or
yarn start
The frontend should open in your browser, typically at http://localhost:3000.

Deployment
This application can be deployed to cloud platforms:

Backend (Spring Boot): Can be deployed on platforms like Render, Heroku, AWS Elastic Beanstalk, etc.

Render Specific: Ensure your MONGODB_URI environment variable is set in Render's dashboard. Your build command will likely be mvn clean package -DskipTests.

Frontend (React): Can be deployed on platforms like Netlify, Vercel, GitHub Pages, etc.

Netlify Specific: Ensure your REACT_APP_API_BASE_URL environment variable is set in Netlify's build settings to point to your deployed backend URL.

Usage
Access the application: Open http://localhost:3000 (or your deployed Netlify URL) in your browser.

Register: Click on "Register here" and create a new account with a unique username, email, and password.

Login: Use your registered email/username and password to log in.

Dashboard: After logging in, you will be redirected to the dashboard where you can manage your wishlists.

Create Wishlists: Add new wishlists.

Add Items: Add items to your wishlists.


Contributing
Contributions are welcome! If you have any suggestions, bug reports, or want to contribute to the codebase, please open an issue or submit a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.


