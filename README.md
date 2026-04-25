# 📚 Online Library Management System (PHP)

A complete web-based **Library Management System** built with **PHP**, **MySQL (PDO)**, **Bootstrap**, and **jQuery**. This application provides separate dashboards and functionalities for **Admin** and **Students (Users)** to efficiently manage library operations including book inventory, issuing, returning, and user management.

---

## 🚀 Live Demo / Screenshots

> The system features a clean, responsive Bootstrap-based UI with an image slider on the homepage, data tables for record management, and AJAX-powered real-time lookups.

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | HTML5, CSS3, Bootstrap 3, jQuery, JavaScript |
| **Backend** | PHP 8.x |
| **Database** | MySQL / MariaDB (via PDO) |
| **Icons** | Font Awesome |
| **Tables** | DataTables (jQuery plugin) |
| **Password Hashing** | MD5 |

---

## ✨ Features

### 👨‍🎓 Student (User) Panel

| Feature | Description |
|---------|-------------|
| **User Registration** | Students can sign up with auto-generated unique Student ID (e.g., `SID002`) |
| **User Login** | Secure login with email and password |
| **Dashboard** | Overview of total books listed, books not returned yet, and total issued books |
| **Browse Books** | View all available books with cover image, author, ISBN, quantity, and availability status |
| **Issued Books** | View personal book issue history with issue date, return date, and fine details |
| **My Profile** | View and update personal details (Name, Mobile Number) |
| **Change Password** | Update password with current password verification |
| **Forgot Password** | Recover password using registered email and mobile number |

### 🔐 Admin Panel

| Feature | Description |
|---------|-------------|
| **Admin Login** | Secure admin authentication |
| **Admin Dashboard** | Quick stats: Total Books, Books Not Returned, Registered Users, Authors, Categories |
| **Category Management** | Add new categories, edit existing ones, activate/deactivate |
| **Author Management** | Add and manage book authors |
| **Book Management** | Add books with image upload, category, author, ISBN, price, and quantity; edit and delete books |
| **Issue Books** | Issue books to students with AJAX-powered student and book lookup |
| **Manage Issued Books** | View all issued books, track returns, and update return status |
| **Return Book with Fine** | Process book returns and collect fines (if any) in USD |
| **Registered Students** | View all registered students, block or activate accounts |
| **Student History** | View complete book issue history of any individual student |
| **Change Password** | Admin can change their own password |

---

## 🗂️ Project Structure

```
Online-Library-Management-System-PHP/
│
├── library/                          # Main application folder
│   ├── index.php                     # Student login page (with image slider)
│   ├── signup.php                    # Student registration page
│   ├── dashboard.php                 # Student dashboard
│   ├── listed-books.php              # Browse all available books
│   ├── issued-books.php              # View student's issued books
│   ├── my-profile.php                # Student profile management
│   ├── change-password.php           # Student change password
│   ├── user-forgot-password.php      # Student password recovery
│   ├── adminlogin.php                # Admin login page
│   ├── logout.php                    # User logout
│   ├── check_availability.php        # AJAX: check email availability
│   ├── studentid.txt                 # Counter file for auto Student ID generation
│   │
│   ├── includes/
│   │   ├── config.php                # Database configuration (PDO)
│   │   ├── header.php                # Common header & navigation
│   │   └── footer.php                # Common footer
│   │
│   ├── assets/                       # Frontend assets (Bootstrap, CSS, JS, Images)
│   │   ├── css/
│   │   ├── js/
│   │   ├── fonts/
│   │   └── img/
│   │
│   ├── admin/                        # Admin panel
│   │   ├── index.php                 # Admin login
│   │   ├── dashboard.php             # Admin dashboard
│   │   ├── add-category.php          # Add new category
│   │   ├── manage-categories.php     # Manage categories
│   │   ├── edit-category.php         # Edit category
│   │   ├── add-author.php            # Add new author
│   │   ├── manage-authors.php        # Manage authors
│   │   ├── edit-author.php           # Edit author
│   │   ├── add-book.php              # Add new book with image
│   │   ├── manage-books.php          # Manage books
│   │   ├── edit-book.php             # Edit book details
│   │   ├── change-bookimg.php        # Change book image
│   │   ├── issue-book.php            # Issue book to student
│   │   ├── manage-issued-books.php   # View/manage issued books
│   │   ├── update-issue-bookdeails.php # Return book & collect fine
│   │   ├── reg-students.php          # View registered students
│   │   ├── student-history.php       # View student's issue history
│   │   ├── change-password.php       # Admin change password
│   │   ├── get_student.php           # AJAX: fetch student details
│   │   ├── get_book.php              # AJAX: fetch book details
│   │   ├── check_availability.php    # AJAX: check ISBN availability
│   │   ├── logout.php                # Admin logout
│   │   ├── includes/                 # Admin includes (config, header, footer)
│   │   ├── assets/                   # Admin assets
│   │   └── bookimg/                  # Uploaded book cover images
│   │
│   └── library.sql                   # Complete database dump
│
└── README.md                         # This file
```

---

## ⚙️ Installation Guide

### Prerequisites
- **XAMPP / WAMP / MAMP** or any PHP server with MySQL
- PHP 7.4 or higher
- MySQL 5.7+ or MariaDB 10.4+

### Step-by-Step Setup

1. **Clone or Download** the project to your web server directory:
   ```bash
   # For XAMPP (Windows)
   C:\xampp\htdocs\Online-Library-Management-System-PHP\

   # For WAMP
   C:\wamp\www\Online-Library-Management-System-PHP\
   ```

2. **Import the Database:**
   - Open **phpMyAdmin** (`http://localhost/phpmyadmin`)
   - Create a new database named **`library`**
   - Import the `library.sql` file from the project folder

3. **Database Configuration:**
   - Open `library/includes/config.php`
   - Update credentials if needed (default XAMPP settings):
     ```php
     define('DB_HOST','localhost');
     define('DB_USER','root');
     define('DB_PASS','');       // your MySQL password
     define('DB_NAME','library');
     ```

4. **Run the Application:**
   - Start Apache and MySQL from XAMPP Control Panel
   - Open browser and navigate to:
     ```
     http://localhost/Online-Library-Management-System-PHP/library/
     ```

---

## 🔑 Default Login Credentials

### Admin Login
| Field | Value |
|-------|-------|
| **Username** | `admin` |
| **Password** | `Test@123` |
| **Email** | `admin@gmail.com` |

> **Note:** Admin password is hashed with MD5 in the database.

### Student Login (Pre-registered)
| Email | Password |
|-------|----------|
| `anujk@gmail.com` | `Test@123` |
| `amit@gmail.com` | `Test@123` |
| `john@test.com` | `Test@123` |

> New students can register via the signup page. Passwords are auto-hashed with MD5.

---

## 🗃️ Database Schema

### Tables Overview

| Table | Purpose |
|-------|---------|
| `admin` | Stores admin login credentials |
| `tblstudents` | Stores registered student details |
| `tblcategory` | Stores book categories |
| `tblauthors` | Stores book authors |
| `tblbooks` | Stores book details with image and quantity |
| `tblissuedbookdetails` | Stores book issue and return records with fine |

### Key Relationships
- `tblbooks.CatId` → `tblcategory.id`
- `tblbooks.AuthorId` → `tblauthors.id`
- `tblissuedbookdetails.BookId` → `tblbooks.id`
- `tblissuedbookdetails.StudentID` → `tblstudents.StudentId`

---

## 🔒 Security Features

| Feature | Implementation |
|---------|---------------|
| **SQL Injection Prevention** | PDO Prepared Statements with parameter binding |
| **XSS Prevention** | `htmlentities()` output encoding |
| **Session Management** | PHP sessions for both admin and student authentication |
| **Password Hashing** | MD5 hashing for password storage |
| **Access Control** | Redirects unauthenticated users to login pages |
| **Account Blocking** | Admin can block/unblock student accounts |

---

## 🎯 Key Functionalities Explained

### Auto-Generated Student ID
When a student registers, the system reads from `studentid.txt`, increments the counter, and assigns a unique ID like `SID001`, `SID002`, etc.

### AJAX-Powered Lookups
- **Email Availability Check:** During signup, system checks if email already exists via AJAX.
- **ISBN Availability Check:** During book addition, system checks for duplicate ISBN.
- **Student Lookup:** During book issue, admin enters Student ID and student details load dynamically.
- **Book Lookup:** During book issue, admin enters ISBN/Book ID and book details load dynamically.

### Book Availability Calculation
The system dynamically calculates available book quantity based on:
```
Available = Total Quantity - (Total Issued - Total Returned)
```

### Fine Management
When a book is returned, the admin can enter a fine amount (in USD). This is recorded in the `tblissuedbookdetails.fine` column.

---

## 🖼️ Screenshots Description

| Page | Description |
|------|-------------|
| **Homepage** | Image carousel slider with User Login form |
| **User Dashboard** | 3 stat cards: Books Listed, Not Returned, Total Issued |
| **Listed Books** | Grid view of books with cover images, author, ISBN, quantity |
| **Admin Dashboard** | 5 stat cards: Books, Not Returned, Users, Authors, Categories |
| **Manage Books** | DataTable with book image, name, category, author, ISBN, price, actions |
| **Issue Book** | Form with AJAX lookup for student and book details |
| **Manage Issued Books** | DataTable showing all transactions with return status |

---

## 🤝 Contributing

This is a complete academic project. You can extend it by:
- Adding **email notifications** for due dates
- Implementing **barcode/QR code** scanning for books
- Adding **multi-language support**
- Upgrading password hashing from MD5 to **bcrypt**
- Adding **book reservation** system
- Implementing **overdue fine auto-calculation**

---

## 📜 License

This project is open-source and free to use for educational purposes.

---

## 👨‍💻 Author

Developed as a final academic project for Library Management System using PHP and MySQL.

---

## 📞 Support

For any issues during installation or usage:
1. Ensure Apache and MySQL services are running
2. Verify database credentials in `includes/config.php`
3. Check that the `library` database is properly imported
4. Ensure `studentid.txt` has write permissions (for auto ID generation)
5. Ensure `admin/bookimg/` folder has write permissions (for image uploads)

---

> ⭐ **Feel free to star this project if you find it useful!**

