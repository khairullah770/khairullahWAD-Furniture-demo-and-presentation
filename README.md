# KK Furniture Fusion (PHP Furniture Website)

A multi-page furniture showcase website built with **PHP, HTML, CSS, JavaScript, and MySQL**.  
It includes a homepage, shop, about, blog, contact page, and a basic signup/login flow backed by a database.

---

## Project Overview

This project is a demo website for a furniture brand named **KK Furniture Fusion**.  
The frontend is mostly static and styled with custom CSS, while PHP is used for:

- User registration (`registration.php`)
- Login checks on main pages (`index.php`, `shop.php`, `blog.php`)
- MySQL database connection (`connect.php`)
- Data fetch example (`data.php`)

---

## Features

- Responsive UI with:
  - Header and side navigation
  - Search bar toggle
  - Shopping cart drawer
  - Login form drawer
  - Home hero slider
- Product/category sections in shop page
- About and services section
- Blog listing layout
- Contact form layout with embedded Google Map
- Registration form that inserts user data into MySQL
- Basic login query flow using stored signup records

---

## Tech Stack

- **Frontend:** HTML5, CSS3, JavaScript
- **Backend:** PHP
- **Database:** MySQL / MariaDB
- **Assets:** Local images in `/images`
- **Icons:** Font Awesome CDN

---

## Project Structure

```text
.
├── index.php           # Home page + login handler
├── shop.php            # Shop/catalog page + login handler
├── about.php           # About page
├── blog.php            # Blog page + login handler
├── contact.php         # Contact page
├── registration.php    # User signup form + insert logic
├── connect.php         # Database connection config
├── data.php            # Example DB read script
├── app.js              # UI interactions (drawer toggles, slider)
├── styles.css          # Main site styles
├── reg.css             # Registration page styles
├── signup.sql          # SQL dump for signup table + sample data
└── images/             # Project image assets
```

---

## Prerequisites

Before running locally, make sure you have:

- PHP (8.x recommended)
- MySQL or MariaDB
- A local server environment (XAMPP, WAMP, MAMP, or PHP built-in server)
- phpMyAdmin (optional, but useful for importing SQL)

---

## Local Setup

### 1) Place project in web root

If using XAMPP, place this folder under:

- Windows: `C:\xampp\htdocs\`
- Linux/macOS (similar): your server document root

### 2) Configure database

Create a database and import `signup.sql`.

#### Option A: Use phpMyAdmin
1. Open phpMyAdmin
2. Create a database
3. Open the database
4. Import `signup.sql` from the project root

#### Option B: MySQL CLI
```bash
mysql -u root -p -e "CREATE DATABASE signup;"
mysql -u root -p signup < signup.sql
```

### 3) Update DB name if needed

`connect.php` currently uses:

```php
$dbname = "signup";
```

If your imported DB uses a different name, update this value in `connect.php`.

### 4) Run the project

Open in browser:

```text
http://localhost/[project-folder]/index.php
```

---

## Pages

- `index.php` → Home page
- `shop.php` → Product and category listing
- `about.php` → Brand and services
- `blog.php` → Blog cards
- `contact.php` → Contact form + embedded map
- `registration.php` → User registration

---

## Database Schema (Current)

From `signup.sql`, table `signup` contains:

- `first_name`
- `last_name`
- `phone`
- `address`
- `email` (primary key)
- `password`
- `c_password`

---

## Notes / Limitations

- This is a demo project; many elements are static placeholders.
- Authentication logic is basic and should be improved for production.
- Passwords are currently stored in plain text, which is a critical security risk.
- Do not deploy this project to production without adding password hashing (for example, using PHP `password_hash()`/`password_verify()`), prepared statements, and stronger input validation.

---

## Author

Created by **Khairullah Khaliq** (2024).
