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
  - Click
