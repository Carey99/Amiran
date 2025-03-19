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

📂 Amiran
│── 📄 README.md            # Project Documentation (this file)
│── 📄 .gitignore           # Files to ignore in Git versioning
│── 📄 package.json         # Dependencies and scripts (for Node.js)
│── 📄 server.js            # Entry point for backend
│
├── 📂 config               # Configuration files
│   ├── 📄 db.js            # Database connection setup (MongoDB Atlas)
│   ├── 📄 env.js           # Environment variables configuration
│
├── 📂 models               # Mongoose schemas
│   ├── 📄 User.js          # User schema (Admin, Instructor, Student)
│   ├── 📄 Lesson.js        # Lesson schema (Tracks student progress)
│   ├── 📄 Payment.js       # Payment schema (Tracks transactions)
│
├── 📂 routes               # API Routes
│   ├── 📄 authRoutes.js    # Authentication and authorization routes
│   ├── 📄 studentRoutes.js # Student-related actions (lessons, payments)
│   ├── 📄 adminRoutes.js   # Admin dashboard actions
│   ├── 📄 instructorRoutes.js # Instructor dashboard actions
│
├── 📂 controllers          # Business logic for routes
│   ├── 📄 authController.js    # Handles login, registration
│   ├── 📄 studentController.js # Handles student actions
│   ├── 📄 adminController.js   # Handles admin actions
│   ├── 📄 instructorController.js # Handles instructor actions
│
├── 📂 middleware           # Middleware functions
│   ├── 📄 authMiddleware.js  # Authentication & role-based access control
│   ├── 📄 errorHandler.js    # Global error handling
│
├── 📂 utils                # Utility functions
│   ├── 📄 logger.js         # Logging system
│   ├── 📄 paymentUtils.js   # Payment processing logic
│   ├── 📄 emailService.js   # Email notifications
│
├── 📂 public               # Static assets (if needed)
│   ├── 📂 images           # Store images if necessary
│   ├── 📂 styles           # CSS or frontend assets
│
├── 📂 views                # Frontend templates (if using SSR)
│   ├── 📄 dashboard.ejs    # Admin dashboard page
│   ├── 📄 login.ejs        # Login page
│
├── 📂 logs                 # System logs (optional)
│   ├── 📄 access.log       # Access logs
│   ├── 📄 error.log        # Error logs
│
└── 📂 tests                # Automated tests
    ├── 📄 auth.test.js     # Tests authentication logic
    ├── 📄 student.test.js  # Tests student functionality
    ├── 📄 admin.test.js    # Tests admin functionality
---
📢 *This document will be updated as more features are developed. For contributions, refer to the GitHub repository guidelines.*