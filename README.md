# 🚗 Amiran Driving School Management System Documentation

## 📌 Overview
This documentation covers the structure and functionality of the Driving School Management System, designed to facilitate student registration, lesson tracking, and payments, while providing an administrative dashboard for managing instructors, students, and courses.

## ✨ Features
- **📋 Student Registration**: Allows students to apply for driving courses.
- **🧑‍🏫 Instructor Dashboard**: Displays student progress and payment status.
- **🛠️ Admin Dashboard**: Manages student records, instructors, and payments.
- **👑 Super Admin Role**: Oversees all branches with full privileges.
- **🔒 Lesson Restrictions**: Students must clear payments to access subsequent lessons.
- **🖨️ Printable Receipts**: Per-lesson receipts generated upon marking a lesson as completed.

## 👥 User Roles
### 🔰 Super Admin
- Has full privileges across all branches.
- Can add or remove admins and instructors.
- Can modify student balances, offer discounts, and access all system settings.

### 🏢 Admin
- Can add instructors/staff.
- Can manage student records but **cannot** alter balances or offer discounts.
- Oversees course registrations and lesson tracking.

### 🎓 Instructor
- Can view student progress and initiate payment requests.
- Cannot modify student records or balances.

## 🖥️ Admin Dashboard
The admin dashboard includes:
- **👨‍🎓 Student Categories**:
  - **📚 All Students**: Displays all registered students with their details.
  - **🟢 Current Students**: Displays active students with course progress and balance.
  - **✅ Concluded Students**: Displays students who have completed their courses.
- **👩‍🏫 Instructor Management**:
  - Clicking **Add (+)** opens a form for entering instructor details.
  - Instructors can be assigned to specific courses.
- **💰 Payment Management**:
  - Instructors can trigger M-Pesa payment prompts for students with outstanding balances.
  - Payments are reflected in the database, reducing the student’s balance accordingly.
  - If a student has an unpaid balance from **Lesson 13 onwards**, they are **locked out of subsequent lessons** until payment is made.
- **🖨️ Receipt Generation**:
  - A **printable receipt** is generated for each lesson upon marking it as done.
  - Includes student details, lesson number, date, and payment confirmation.

## 🚀 Future Enhancements
- **🏫 Branch Management**: Additional school branches with separate admins.
- **🔔 Automated Notifications**: Reminders for pending payments and lesson schedules.
- **📊 Advanced Reporting**: Data insights on student progress and financials.

## 🎯 File Structure Breakdown

```plaintext
Amiran/
├── backend/
│   ├── config/
│   │   ├── database.js        # Database connection setup
│   │   ├── redis.js           # Caching configuration
│   ├── controllers/
│   │   ├── studentController.js    # Handles student-related logic
│   │   ├── adminController.js      # Manages admin functionalities
│   │   ├── instructorController.js # Manages instructor operations
│   ├── models/
│   │   ├── studentModel.js    # Defines student schema
│   │   ├── adminModel.js      # Defines admin schema
│   │   ├── instructorModel.js # Defines instructor schema
│   ├── routes/
│   │   ├── studentRoutes.js   # Endpoints for student interactions
│   │   ├── adminRoutes.js     # Endpoints for admin functionalities
│   │   ├── instructorRoutes.js # Endpoints for instructor actions
│   ├── server.js             # Main server entry point
├── frontend/
│   ├── components/
│   │   ├── dashboard/
│   │   │   ├── AdminDashboard.jsx
│   │   │   ├── InstructorDashboard.jsx
│   │   │   ├── StudentDashboard.jsx
│   │   ├── payments/
│   │   │   ├── PaymentForm.jsx
│   │   │   ├── Receipt.jsx
│   ├── pages/
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   ├── Home.jsx
│   │   ├── Lessons.jsx
│   │   ├── Payments.jsx
│   ├── App.js                 # Main React component
├── public/
│   ├── index.html             # HTML entry point
│   ├── assets/                # Contains images, logos, etc.
├── .env                       # Environment variables
├── package.json               # Project dependencies
├── README.md                  # Documentation
```
---
📢 *This document will be updated as more features are developed. For contributions, refer to the GitHub repository guidelines.*