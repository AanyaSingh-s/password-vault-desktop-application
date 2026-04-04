# 🔐 Password Vault Desktop Application


A professional, role-based password management system designed for maximum security and modularity. This application implements industry-standard encryption protocols and a clean, persona-driven architecture.

---

## 🏗️ Architecture 

This project was developed by redistributing logic across five distinct developer personas, each responsible for a critical layer of the application:

### 🛠️ Infrastructure & Database Architect
**Focus:** Foundation, Database Schema, and Core Security.
- **SQLite Schema:** Designed a normalized database with indices for high-performance lookups.
- **AES-256 Encryption:** Implemented high-level password storage using the standard **Java Cryptography Extension (JCE)**.
- **BaseDAO:** Created an abstract persistence layer for consistent data access.

### 🔑 Authentication & Security Specialist 
**Focus:** User Identity, Sessions, and BCrypt Hashing.
- **BCrypt Hashing:** Implemented salted password hashing for user accounts.
- **Session Management:** Developed a thread-safe singleton for tracking active user states.
- **Audit Logging:** Integrated a security event tracker that records every login/action.

### 📂 Core Password Core Development
**Focus:** Business Logic, CRUD, and Generation.
- **Secure CRUD:** Developed the primary service for adding, viewing, and deleting sensitive entries.
- **Password Generator:** Integrated a cryptographically secure random password generator.
- **Model Design:** Crafted the `PasswordEntry` and `Category` data models with validation.

### 🔍 Data Management & Reporting 
**Focus:** Advanced Search, Filtering, and Portability.
- **Search Engine:** Built a full-text search engine with relevance scoring (Website > Username).
- **Export/Import:** Created an encrypted custom file format for secure data migration.
- **Dynamic Filters:** Developed a builder for complex category and date-based filtering.

### 🎨 UX/UI & Frontend Development
**Focus:** Swing GUI, Responsive Design, and User Flow.
- **Modular Windows:** Designed specialized screens for Login, Registration, and the Main Dashboard.
- **UI Consistency:** Implemented a `DialogFactory` for unified styling and solid-colored buttons.
- **Responsive Layouts:** Ensured a clean, intuitive experience across different window sizes.

---

## 🛡️ Security Implementation

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **User Auth** | BCrypt  | Irreversible hashing for master passwords. |
| **Data Storage** | AES-256 (JCE) | Encryption of website credentials. |
| **Persistence** | SQLite | Local, encrypted file-based database. |
| **Integrity** | PRAGMA Foreign Keys | Enforcing data relationships in the vault. |

---

## 🚀 Getting Started

### Prerequisites
- JDK 1.8 or higher.
- Apache Maven 3.x.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/AanyaSingh-s/password-vault-desktop-application.git
   ```
2. Navigate to the root directory:
   ```bash
   cd "password vault desktop application"
   ```
3. Build and Run:
   ```bash
   mvn clean compile exec:java
   ```

### First-Time Use
1. **Register:** Launch the app and click **Register** to create your local master account.
2. **Login:** Enter your credentials to unlock the vault.
3. **Manage:** Start adding your website credentials. Everything is encrypted on-the-fly.

---

## 📂 Project Structure

```text
src/main/java/com/passwordvault/
├── infrastructure/         # (Foundation)
│   ├── db/                 # Connection & Schema Management
│   ├── security/           # AES-256 implementation
│   ├── data/               # BaseDAO abstraction
│   └── exception/          # Centralized error handling
├── auth/                   # (Security & Identity)
│   ├── dao/                # User persistence
│   ├── service/            # Login/Registration flows
│   ├── security/           # BCrypt logic
│   ├── logging/            # Audit tracking
│   ├── session/            # Session lifecycle
│   └── util/               # Password validation
├── core/                   # (Business Logic)
│   ├── model/              # Core data models
│   ├── dao/                # Password entry persistence
│   └── service/            # High-level password operations
├── data/                   # (Reporting)
│   ├── service/            # Search & Portability (Export/Import)
│   └── util/               # Advanced filtering builders
└── ui/                     # (Presentation)
    ├── LoginWindow.java    # Authentication screen
    ├── MainWindow.java     # Primary dashboard
    ├── DialogFactory.java  # UI utility factory
    └── PasswordVaultApp.java # Entry point
```

---

