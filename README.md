# 🍰 CakePHP Project Setup Guide

This guide helps you set up and run a CakePHP project locally using **XAMPP**, **Composer**, and **VS Code**.

---

## ✅ Prerequisites

Make sure you have the following installed:

- [XAMPP](https://www.apachefriends.org) – for Apache + MySQL
- [Composer](https://getcomposer.org) – PHP dependency manager
- [VS Code](https://code.visualstudio.com) – code editor
- PHP ≥ 7.4 (included in XAMPP)

---

## 📁 1. Start Your CakePHP Project

### 🔧 Option A: Create a new CakePHP project
```bash
composer create-project --prefer-dist cakephp/app cakephp-app
```
This creates a fresh CakePHP project named cakephp-app.

## 📂 Option B: Use an existing CakePHP project
Copy your CakePHP project folder (e.g. cakephp-app) into:
```
C:\xampp\htdocs\
```
## 💻 2. Open the project in VS Code
```
cd C:\xampp\htdocs\cakephp-app
code .
```
## 📦 3. Install Composer Dependencies
```
composer install
```
## ⚙️ 4. Configure the Database Connection
Edit the file config/app_local.php and set your database credentials like this:
```
'Datasources' => [
    'default' => [
        'host' => 'localhost',
        'username' => 'root',
        'password' => '',
        'database' => 'cakephp_db',
        'driver' => 'Cake\Database\Driver\Mysql',
    ],
],
```
Create the database (cakephp_db) using phpMyAdmin or MySQL CLI before migrating.

## 🗂️ 5. Create Missing Migrations Folder (if needed)
```
mkdir config\Migrations
```
## 🔄 6. Run Database Migrations
```
bin/cake migrations migrate
```
This sets up your tables in the database.

## 🚀 7. Run the CakePHP Development Server
```
bin/cake server
```
Visit your app in the browser:
```
http://localhost:8765
```

# Step-by-Step MySQL Shell Access Command (XAMPP)

🔹 **1. Open Git Bash or MobaXterm**  
Navigate to your MySQL folder (XAMPP default path):

```bash
cd /c/xampp/mysql/bin
```
### 🔹 2. Access MySQL Shell
```
./mysql -u root -p
```
### 🔹 3. List All Databases
```
SHOW DATABASES;
```
### 🔹 4. Use a Database
For example, if your database is named cakephp_app:
```
USE cakephp_app;
```
### 🔹 5. Show All Tables
```
SHOW TABLES;
```
Table details For 'students' table:
```
select * from students;
```
### 🔹 6. Exit MySQL
```
exit
```
