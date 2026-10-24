# Lab Exam - Quero

**Full Name:** Jonathan Quero

## Project Description

This project is a Laravel-based Student Management System developed as part of a practical examination. It manages student records and courses and demonstrates authentication, authorization, database relationships, and API authentication using Laravel Sanctum.

## Technologies Used

- PHP 8.2
- Laravel 12
- MySQL
- Laravel Sanctum
- Composer
- Git and GitHub

## Prerequisites

Install the following before running the project:

- XAMPP with MySQL
- PHP 8.2 or a compatible version
- Composer
- Git
- Visual Studio Code

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/JnathanQ/lab-exam-quero.git
cd lab-exam-quero
```

If the project is already on your computer, open its existing folder instead.

### 2. Install dependencies

```bash
composer install
```

### 3. Configure the environment

Create a local environment file:

```bash
copy .env.example .env
```

Generate the application key:

```bash
php artisan key:generate
```

### 4. Configure the database

Create a MySQL database named `lab_exam_quero` using phpMyAdmin or MySQL.

Update the database settings in your local `.env` file:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=lab_exam_quero
DB_USERNAME=root
DB_PASSWORD=
```

Adjust the username and password to match your local MySQL configuration.

### 5. Run database migrations

```bash
php artisan migrate
```

### 6. Start the development server

```bash
php artisan serve
```

Open the application at:

http://127.0.0.1:8000

## API Authentication

The project includes Laravel Sanctum token authentication.

### Create an API token

Send a POST request to:

`http://127.0.0.1:8000/api/tokens/create`

Provide the user's email and password in a JSON request body:

```json
{
  "email": "admin@example.com",
  "password": "YOUR_ACTUAL_PASSWORD"
}
```

Replace the example credentials with valid local test-account credentials.

A successful request returns a plain-text API token.

### Retrieve students

Send a GET request to:

`http://127.0.0.1:8000/api/students`

Include the token in the request header:

```text
Authorization: Bearer YOUR_API_TOKEN
Accept: application/json
```

A valid token returns student records with their associated courses. A request without a valid token should return HTTP 401 Unauthorized when JSON is requested.

## Security
