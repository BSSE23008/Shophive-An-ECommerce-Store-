# 🛒 Shophive - Multi-Vendor E-Commerce Web Application

**Shophive** is a **multi-vendor e-commerce platform** built using **PHP (MVC architecture)** and **MySQL**. It allows multiple sellers to list products while customers can browse, search, and purchase items. Features include cart management, order processing, payments, and product reviews.

---

## 📌 Features

### ✅ Customer Features
- User Registration & Login
- Product Catalog Browsing
- Product Search with Live Filtering
- Add to Cart / Update Quantity / Remove Items
- Place Orders & View Order History
- Leave Reviews on Purchased Products
- Wishlist Management
- Profile Management

### ✅ Seller Features
- Seller Registration & Login
- Add / Update / Delete Products
- Inventory Management
- Track Orders Received from Customers
- Sales Analytics Dashboard
- Product Category Management

### ✅ Admin/Optional Features
- Extendable for admin dashboard for managing sellers, orders, and site-wide statistics
- User Management
- Category Management
- Payment Processing
- Order Management System

---

## 🗃️ Database Schema Overview

| Table        | Purpose                              |
|--------------|--------------------------------------|
| `Customer`   | Stores customer data                 |
| `Seller`     | Stores seller-specific info          |
| `Category`   | Product categories and subcategories |
| `Product`    | All products listed by sellers       |
| `Cart`       | Shopping carts for customers         |
| `CartItem`   | Items in each cart                   |
| `Orders`     | Master table for placed orders       |
| `OrderItem`  | Each product in an order             |
| `Payment`    | Payment records and transactions     |
| `Review`     | Customer reviews of products         |
| `Wishlist`   | Customer wishlists                   |

---

## 🖥️ Technologies Used
- **Backend:** PHP 8.0+ (MVC Pattern)
- **Frontend:** HTML5, CSS3, Bootstrap 5, JavaScript
- **Database:** MySQL 8.0+
- **Tools:** PDO for database interaction, Sessions for authentication

---

## 🚀 Installation and Setup

### Prerequisites
- **PHP 8.0+** with the following extensions:
  - PDO
  - PDO_MySQL
  - mbstring
  - openssl
  - curl
  - gd (for image processing)
- **MySQL 8.0+** or **MariaDB 10.4+**
- **Apache/Nginx** web server
- **Composer** (for dependency management)

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/shophive.git
cd shophive
```

### Step 2: Install Dependencies
```bash
composer install
```

### Step 3: Database Setup
1. Create a new MySQL database:
```sql
CREATE DATABASE shophive;
```

2. Import the database schema:
```bash
mysql -u your_username -p shophive < database/shophive_schema.sql
```

### Step 4: Configuration
1. Copy the configuration template:
```bash
cp config/config.example.php config/config.php
```

2. Edit `config/config.php` with your database credentials:
```php
<?php
define('DB_HOST', 'localhost');
define('DB_NAME', 'shophive');
define('DB_USER', 'your_username');
define('DB_PASS', 'your_password');
define('DB_CHARSET', 'utf8mb4');

// Application settings
define('APP_NAME', 'Shophive');
define('APP_URL', 'http://localhost/shophive');
define('UPLOAD_PATH', 'public/images/uploads/');
?>
```

### Step 5: Set Permissions
```bash
chmod -R 755 public/images/uploads/
chmod -R 644 config/
```

### Step 6: Web Server Configuration

#### Apache (.htaccess)
The project includes an `.htaccess` file for URL rewriting. Ensure `mod_rewrite` is enabled:
```bash
sudo a2enmod rewrite
sudo systemctl restart apache2
```

#### Nginx
Add this to your Nginx server block:
```nginx
location / {
    try_files $uri $uri/ /index.php?$query_string;
}

location ~ \.php$ {
    fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
    fastcgi_index index.php;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    include fastcgi_params;
}
```

### Step 7: Access the Application
1. Open your web browser
2. Navigate to `http://localhost/shophive` (or your configured domain)
3. You should see the Shophive homepage

### Step 8: Create Admin/Test Accounts
1. Register as a customer: `http://localhost/shophive/customer/register`
2. Register as a seller: `http://localhost/shophive/seller/register`
3. Use the sample data provided in the SQL schema for testing

---

## 📱 Usage Examples

### Customer Workflow
1. Register/Login as customer
2. Browse products by category
3. Search for specific products
4. Add products to cart
5. Proceed to checkout
6. Place order and make payment
7. Track order status
8. Leave product reviews

### Seller Workflow
1. Register/Login as seller
2. Set up seller profile
3. Add product categories
4. List products with images
5. Manage inventory
6. Process customer orders
7. Update order status
8. View sales analytics

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Coding Standards
- Follow PSR-12 coding standards
- Use meaningful variable and function names
- Add comments for complex logic
- Write unit tests for new features

---

## 👨‍💻 Developer

**Developed by:** Ahmad Khan  
**Email:** ahmadumer8595@gmail.com  
**LinkedIn:** https://www.linkedin.com/in/ahmad-khan-60ab33235/  
**GitHub:** https://github.com/BSSE23008  
**Location:** Lahore, Punjab, Pakistan

### About the Developer
I am a passionate full-stack developer specializing in PHP, MySQL, and modern web technologies. With expertise in building scalable e-commerce solutions and multi-vendor platforms, I focus on creating robust, user-friendly applications that drive business growth.

**Skills:** PHP, MySQL, JavaScript, HTML5, CSS3, Bootstrap, MVC Architecture, RESTful APIs, Payment Gateway Integration, Database Design

---

## 🙏 Acknowledgments

- Bootstrap team for the responsive framework
- Font Awesome for the icon library
- PHP community for excellent documentation
- Open source contributors who inspire continuous learning

---

## 📞 Support

For support, email [ahmadumer8595@gmail.com] or create an issue in the GitHub repository.

---

*Made with ❤️ in Lahore, Pakistan*