# Wishlist Application
This app is hosted in web
---
Link to the app: https://wishlist-frontend.netlify.app/
---
A full-stack web application for users to create, manage, and share their personal wishlists.

---

### ⚙️ Backend Setup

1. **Clone the repository**  
   

2. **Configure MongoDB Connection**  
   - Create an account on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)  
   - Create a new cluster  
   - Go to **Database Access** → Add a new user  
   - Go to **Network Access** → Add your IP address or allow access from anywhere (for development)  
   - Go to **Databases** → **Connect** → Choose **"Connect your application"** and copy the connection string  
     ```
     mongodb+srv://<username>:<password>@cluster0.mongodb.net/
     ```
   - Create or edit the file:  
     `src/main/resources/application.properties`  
     And add:
     ```properties
     spring.data.mongodb.uri=mongodb+srv://<username>:<password>@cluster0.mongodb.net/wishlistdb?retryWrites=true&w=majority
     ```
   > 🔐 **Important:** Replace `<username>`, `<password>`, and cluster URL with your actual MongoDB credentials.

3. **Build & Run the Backend**
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```
   - The backend server will start on: `http://localhost:8080`

---

### 🌐 Frontend Setup

1. **Navigate to Frontend Directory**  
   ```bash
   cd ../wishlist-frontend
   ```

2. **Install Dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Configure API Base URL**
   - Create a `.env` file in the `wishlist-frontend` root directory  
   - Add your backend base URL:
     ```env
     REACT_APP_API_BASE_URL=http://localhost:8080/api
     ```
   - For Render deployment:
     ```env
     REACT_APP_API_BASE_URL=https://your-render-app-url.onrender.com/api
     ```

4. **Run Development Server**
   ```bash
   npm start
   # or
   yarn start
   ```
   - The app will open at: `http://localhost:3000`

---

## ☁️ Deployment

### 🔙 Backend (Spring Boot)

- Can be deployed on:
  - **Render**
  - **Heroku**
  - **AWS Elastic Beanstalk**
- **Render specific instructions:**
  - Set environment variable: `MONGODB_URI`
  - Build command:
    ```bash
    mvn clean package -DskipTests
    ```

### 🔜 Frontend (React)

- Can be deployed on:
  - **Netlify**
  - **Vercel**
  - **GitHub Pages**
- **Netlify specific instructions:**
  - Set environment variable: `REACT_APP_API_BASE_URL` in Netlify build settings

---

## 📋 Usage

1. Open the app at `http://localhost:3000` or your deployed frontend URL  
2. **Register** a new user  
3. **Log in** with your credentials  
4. Access your **Dashboard** to:
   - Create wishlists  
   - Add/edit/remove items  

---

## 🤝 Contributing

Contributions are welcome!  
If you have suggestions, bug fixes, or new features, please open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the **MIT License**.  
See the [LICENSE] file for details.
