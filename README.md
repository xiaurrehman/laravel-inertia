# Laravel Inertia CRUD App

![App Screenshot](https://raw.githubusercontent.com/xiaurrehman/laravel-inertia/main/public/images/Screenshot.png)

A simple and clean CRUD (Create, Read, Update, Delete) application built with **Laravel**, **Vue 3**, **Inertia.js**, and **Vite**.

## 🛠️ Features

- Laravel 10 backend
- Vue 3 frontend with Inertia.js
- Tailwind CSS styling
- Vite for frontend tooling
- CRUD operations with clean UI
- Form validation (client + server side)
- Responsive layout

## 📦 Requirements

- PHP >= 8.1
- Composer
- Node.js (v18+ recommended)
- MySQL or PostgreSQL
- Laravel CLI

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/xiaurrehman/laravel-inertia.git

cd laravel-inertia-crud

# Install PHP dependencies
composer install

# Install JS dependencies
npm install

# Copy .env file and configure
cp .env.example .env
php artisan key:generate

# Configure database in .env
DB_DATABASE=your_database
DB_USERNAME=your_username
DB_PASSWORD=your_password

# Run migrations
php artisan migrate

# Compile assets
npm run dev

# Start the server
php artisan serve
