# Password Vault Desktop Application

A highly secure, role-based password management system built with Java and Swing. This project demonstrates a modular architecture with a clear separation of concerns across five core development roles.

## 🔐 Security Features

- **AES-256 Encryption:** All stored passwords are encrypted using the standard Java Cryptography Extension (JCE).
- **BCrypt Hashing:** User authentication is secured with salted BCrypt hashes.
- **SQLite Persistence:** Lightweight, portable database management.
- **Session Management:** Secure tracking of user sessions and logout flows.
- **Audit Logging:** Security events are logged for accountability.

## 🏛️ Project Architecture (Persona-Based)

The codebase is divided into five distinct modules, each representing a developer role:

1.  **Infrastructure (Person 1):** Database schema, connection management, and AES-256 encryption foundation.
2.  **Authentication (Person 2):** User registration, login, BCrypt hashing, and session management.
3.  **Core Management (Person 3):** Password entry CRUD operations, secure password generation, and category management.
4.  **Data Services (Person 4):** Advanced search with relevance scoring, filtering, and encrypted Export/Import functionality.
5.  **GUI & UX (Person 5):** Desktop interface featuring separate Login, Registration, and Dashboard windows.

## 🚀 Getting Started

### Prerequisites
- JDK 1.8 or higher
- Apache Maven

### Installation & Run
1.  **Extract/Clone** the repository.
2.  Navigate to the project directory.
3.  **Build and Run:**
    ```bash
    mvn clean compile
    mvn exec:java
    ```

### Usage
- **Registration:** New users must click "Register" to create a local vault account.
- **Logging In:** Use your credentials to access the secure dashboard.
- **Adding Entries:** Click "+ Add New" to store a website, username, and password. Data is encrypted instantly using AES-256.

## 📁 Package Structure
- `com.passwordvault.infrastructure`: Database and Encryption Foundation
- `com.passwordvault.auth`: Security and User Management
- `com.passwordvault.core`: Main Password Management Logic
- `com.passwordvault.data`: Search and Data Export Services
- `com.passwordvault.ui`: Swing-based User Interface Components
