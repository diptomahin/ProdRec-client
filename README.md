### 1. **Project Name**:

- ProdRec

- #### 🚀 **Live Page Link to the Deployed Project**
  - https://prodrec-4d9f0.firebaseapp.com/
- #### 🚀 **Server Side Link to the Deployed Project**
  - https://prod-rec-server-site.vercel.app/

### 2. 📝 **Project Description**

ProdRec is a dynamic recommendation platform designed to enhance decision-making for users exploring products. Built using React, Tailwind CSS, DaisyUI, Firebase, and MongoDB, ProdRec allows users to submit queries about products and receive personalized recommendations from others.

The platform offers a seamless experience for managing queries and recommendations, featuring user authentication and a clean, responsive interface. With advanced features like timestamped queries, categorized search, and recommendation tracking, ProdRec is a versatile tool for users seeking trusted product suggestions


### 3. 🛠️ **Technologies Used**

### **Frontend**

- [React](https://reactjs.org/) – Component-based UI library.
- [Tailwind CSS](https://tailwindcss.com/) – Utility-first CSS framework.
- [DaisyUI](https://daisyui.com/) – Pre-styled Tailwind components.
- [React Router](https://reactrouter.com/) – Client-side routing.

### **Backend & Database**

- [Firebase](https://firebase.google.com/) – Authentication and real-time database.
- [MongoDB](https://www.mongodb.com/) – NoSQL database for storing product and order details.
- [NodeJs](https://nodejs.org/en) – NoSQL database for storing product and order details.
- [Express](https://expressjs.com/en/starter/hello-world.html) – NoSQL database for storing product and order details.


### 4. Web App Project Structure

## 🌐 Layout & Page Structure

### 🧭 Main Layout
- **Header (Navbar)**
  - Website Logo + Name
  - Navigation (conditionally based on login status):
    - **Not Logged In:**
      - Home
      - Queries
      - Login
    - **Logged In:**
      - Home
      - Queries
      - Recommendations For Me
      - My Queries
      - My Recommendations
      - Logout

- **Footer**
  - Website logo + name
  - © Copyright
  - Social Media Links:
    - Facebook
    - LinkedIn

---

### ❌ 404 Error Page
- Message: “Page not found”
- Button: “Back to Homepage” → Redirects to `/`

---

## 🔐 Login & Registration System

### 🔑 Login Page
- Email/Password login
- Google sign-in
- Link to Registration page

### 📝 Registration Page
- Fields:
  - Name
  - Email
  - Password
  - Photo URL
- No email verification or password reset required (for now)

---

## 🏠 Home Page (Landing Page)

### 🎞️ Slider
- Use beautiful, relevant images to express the purpose of your website

### 🆕 Recent Queries
- Display the 6 most recent queries (added from Add Query page) in card format

### ➕ Two Extra Sections
- Add 2 creative and animated sections
- Ideas: Trending Boycotts, Global Impact Tracker

---

## 🔒 Private Routes

### ➕ Add Query Page
- Accessible only from "My Queries" page
- **Form Fields:**
  - Product Name
  - Product Brand
  - Product Image URL
  - Query Title (e.g., *Is there a better product with same quality?*)
  - Boycotting Reason (details)
- **Store with:**
  - User Email
  - User Name
  - User Profile Photo (from Firebase)
  - Current Date/Time (`Date.now()`)
  - `recommendationCount` (default: 0)

---

### 📁 My Queries Page
- **Banner**: Stylish heading + “Add Query” button
- **Display Queries:**
  - User's own queries in 1/2/3-column card layout
  - Sorted in descending order by timestamp
  - Each card shows:
    - View Details → Navigate to detail page
    - Update → Modal or separate route
    - Delete → Confirmation popup
- If none exist: Show message + “Add Query” button

---

## 📰 Queries Page
- Public route
- Display all queries in card format (1/2/3 column layout)
- Each card includes:
  - Query details
  - `recommendationCount`
  - Recommend Button → Navigates to query details page

---

## 📄 Query Details Page
- Show:
  - Full query details
  - User info (who created it)

### ➕ Add Recommendation Form
- **Fields:**
  - Recommendation Title
  - Recommended Product Name
  - Recommended Product Image
  - Recommendation Reason
- On submit:
  - Save recommendation with:
    - `queryId`
    - `queryTitle`
    - `productName`
    - `userEmail` (creator)
    - `userName` (creator)
    - `recommenderEmail` (logged-in user)
    - `recommenderName` (logged-in user)
    - Current timestamp
  - **Increment** query’s `recommendationCount` using MongoDB `$inc` operator

### 💬 All Recommendations (for this query)
- Display like comments
- Include:
  - Image
  - Recommendation details
  - Recommender info
  - Date

---

## 🙋‍♂️ My Recommendations
- Private route
- Show all recommendations by the logged-in user in a **table format**
- **Actions:**
  - Delete recommendation with confirmation
    - After deletion, **decrement** the `recommendationCount` of the related query

---

## 🎯 Recommendations For Me
- Private route
- Show all recommendations made **by others** for the user’s queries
- Display in table format with relevant details

---

## ✅ Notes
- Use `Date.now()` or `new Date()` for timestamps
- Use Firebase Auth for login/logout/auth state
- Use MongoDB `$inc` to increment/decrement counts



