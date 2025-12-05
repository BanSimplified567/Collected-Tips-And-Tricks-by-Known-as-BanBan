# Learn to used .env file on your project
# Using `.env` Files in React (Vite) + PHP + MySQL Projects

## 1. Purpose of `.env` in This Stack

* **Frontend (React Vite):** Store environment-specific values such as API base URLs.
* **Backend (PHP):** Store sensitive credentials like database username/password.

This keeps secrets out of your code and allows easy switching between development and production.

---

## 2. Backend (PHP + MySQL) Example

### Step 1: Create `.env` file in your PHP project root

```env
# .env
DB_HOST=localhost
DB_NAME=mydatabase
DB_USER=root
DB_PASS=secret
```

### Step 2: Install PHP dotenv library (via Composer)

```bash
composer require vlucas/phpdotenv
```

### Step 3: Load `.env` in PHP

```php
<?php
require_once __DIR__ . '/vendor/autoload.php';

$dotenv = Dotenv\Dotenv::createImmutable(__DIR__);
$dotenv->load();

// Access environment variables
$host = $_ENV['DB_HOST'];
$db   = $_ENV['DB_NAME'];
$user = $_ENV['DB_USER'];
$pass = $_ENV['DB_PASS'];

// Connect to MySQL
try {
    $pdo = new PDO("mysql:host=$host;dbname=$db", $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Database connected successfully!";
} catch (PDOException $e) {
    echo "Connection failed: " . $e->getMessage();
}
```

✅ This keeps your database credentials secure and outside the PHP code.

---

## 3. Frontend (React Vite) Example

### Step 1: Create `.env` file in the Vite project root

```env
# .env
VITE_API_BASE_URL=http://localhost:8000/api
```

> **Note:** In Vite, environment variables must start with `VITE_` to be exposed to the frontend.

### Step 2: Access `.env` variables in React

```javascript
// src/api.js
const API_BASE_URL = import.meta.env.VITE_API_BASE_URL;

export const fetchUsers = async () => {
  const response = await fetch(`${API_BASE_URL}/users.php`);
  const data = await response.json();
  return data;
};
```

### Step 3: Use in a component

```javascript
// src/App.jsx
import React, { useEffect, useState } from "react";
import { fetchUsers } from "./api";

function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetchUsers().then(setUsers);
  }, []);

  return (
    <div>
      <h1>Users List</h1>
      <ul>
        {users.map(user => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

---

## 4. PHP API Example

```php
<?php
header('Content-Type: application/json');
require_once '../vendor/autoload.php';

$dotenv = Dotenv\Dotenv::createImmutable(__DIR__ . '/../');
$dotenv->load();

$host = $_ENV['DB_HOST'];
$db   = $_ENV['DB_NAME'];
$user = $_ENV['DB_USER'];
$pass = $_ENV['DB_PASS'];

try {
    $pdo = new PDO("mysql:host=$host;dbname=$db", $user, $pass);
    $stmt = $pdo->query("SELECT id, name FROM users");
    $users = $stmt->fetchAll(PDO::FETCH_ASSOC);
    echo json_encode($users);
} catch (PDOException $e) {
    echo json_encode(['error' => $e->getMessage()]);
}
```

---

## 5. Key Points

1. **Backend:** `.env` stores secrets like database credentials. PHP uses `vlucas/phpdotenv` to load them.
2. **Frontend:** `.env` stores environment variables like API URLs. Vite exposes variables prefixed with `VITE_`.
3. **Security:** Never commit `.env` to Git. Add it to `.gitignore`.
4. **Flexibility:** Easy to switch between environments (local, staging, production) by creating `.env.local`, `.env.production`, etc.

---

Using `.env` files keeps your configuration organized, secure, and adaptable across different environments.
