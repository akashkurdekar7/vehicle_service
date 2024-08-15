# Vehicle Service Management System

## Overview

The **Vehicle Service Management System** is designed to facilitate the management of vehicle service requests, maintain a list of mechanics, and handle various service-related operations efficiently. This system includes features for managing service categories, requests, mechanics, and user authentication.

## Features

- **Service Categories:** Organize and manage different types of vehicle categories.
- **Mechanics Management:** Maintain detailed records of mechanics including contact information.
- **Service Requests:** Create, view, and manage service requests.
- **Metadata Management:** Store additional metadata related to each service request.
- **User Authentication:** Admin and client login functionalities with session management.
- **System Settings:** Configure and manage system-wide settings and preferences.

## Installation

### Prerequisites

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Apache or Nginx web server

### Steps

1. **Clone the Repository**

    ```bash
    git clone https://github.com/yourusername/vehicle-service-management-system.git
    ```

2. **Navigate to the Project Directory**

    ```bash
    cd vehicle-service-management-system
    ```

3. **Set Up the Database**

    Import the provided SQL dump (`sql/database_dump.sql`) into your MySQL database:

    ```bash
    mysql -u yourusername -p yourdatabase < sql/database_dump.sql
    ```

4. **Configure Database Connection**

    Update the `config.php` file with your database credentials:

    ```php
    define('DB_SERVER', 'localhost');
    define('DB_USERNAME', 'yourusername');
    define('DB_PASSWORD', 'yourpassword');
    define('DB_NAME', 'vehicle_service_db');
    ```

5. **Set File Permissions**

    Ensure the web server has the appropriate permissions to access necessary files and directories.

6. **Run the Application**

    Access the application via your web server. For example:

    ```
    http://localhost/vehicle-service-management-system/
    ```

## File Structure

- **`/config.php`:** Contains database configuration settings.
- **`/initialize.php`:** Initialization script for the application.
- **`/classes/`:** Directory containing PHP classes (`DBConnection.php`, `Login.php`).
- **`/sql/`:** Directory containing SQL dump file (`database_dump.sql`).
- **`/public/`:** Public-facing files and assets.

## PHP Classes

### `DBConnection`

Manages the database connection.

- **Constructor:** Initializes the connection to the database.
- **Destructor:** Closes the database connection when no longer needed.

### `Login`

Handles user authentication and session management.

- **Constructor:** Sets up the database connection and configuration.
- **Methods:**
  - `index()`: Displays an access denied message.
  - `login()`: Authenticates user login.
  - `logout()`: Logs out the user.
  - `login_user()`: Authenticates client login.

## Security Notes

- **Password Handling:** MD5 is used for password hashing. For improved security, consider using PHP’s `password_hash()` and `password_verify()` functions.
- **SQL Injection Prevention:** Ensure that all user inputs are sanitized and parameterized queries are used to prevent SQL injection.

## Contributing

1. **Fork the Repository**
2. **Create a New Branch**

    ```bash
    git checkout -b feature/your-feature
    ```

3. **Make Changes and Commit**

    ```bash
    git commit -am 'Add new feature'
    ```

4. **Push to the Branch**

    ```bash
    git push origin feature/your-feature
    ```

5. **Create a New Pull Request**

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

Inspired by various open-source projects and frameworks.

