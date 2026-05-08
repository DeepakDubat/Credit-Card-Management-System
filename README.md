# 💳 Credit Card Management System

A robust, feature-rich **Credit Card Management System** built in Java with MySQL backend, enabling users to manage credit card accounts, track transactions, handle billing cycles, EMI conversions, and perform secure card operations — all through an intuitive console-based interface. This project demonstrates core Java concepts including OOP principles, JDBC connectivity, DAO design pattern, layered architecture, and MySQL database integration.

---

## 🔗 Repository

> **GitHub:** [github.com/DeepakDubat](https://github.com/DeepakDubat)

---

## ✨ Features

| Module | Functions |
|---|---|
| **👤 User Management** | Register, Login, Update Profile, Change Password, Delete Account |
| **💳 Card Management** | Apply, Issue (Admin), Block, Unblock, Credit Limit Update |
| **💸 Transactions** | Purchase, Cash Advance (3% fee), Payment, Refund, History |
| **🧾 Billing** | Generate Bill, Pay Bill, Convert to EMI (1.5%/month) |
| **🔐 Security** | Set PIN, OTP Generation, Lock/Unlock Card |
| **📊 Reports** | Monthly Summary, Spending Analysis, Admin Dashboard |

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| **Language** | Java SE 11+ |
| **Database** | MySQL |
| **IDE** | Apache NetBeans |
| **Connectivity** | JDBC (MySQL Connector/J) |

---

## 📁 Project Structure

```
Credit card management system/
├── schema.sql                   ← Run this in MySQL Workbench FIRST
├── build_and_run.bat            ← Alt: compile & run from command line
├── lib/
│   └── mysql-connector-j.jar   ← Download and place here
└── src/
    ├── models/
    │   ├── User.java
    │   ├── CreditCard.java
    │   ├── Transaction.java
    │   └── Bill.java
    ├── dao/
    │   ├── DBConnection.java    ← UPDATE password here
    │   ├── UserDAO.java
    │   ├── CreditCardDAO.java
    │   ├── TransactionDAO.java
    │   └── BillDAO.java
    ├── services/
    │   ├── UserService.java
    │   ├── CardService.java
    │   ├── TransactionService.java
    │   ├── BillingService.java
    │   ├── SecurityService.java
    │   └── ReportService.java
    └── ui/
        ├── Main.java            ← Entry point (Main class)
        ├── AdminMenu.java
        └── CustomerMenu.java
```

---

## 🚀 Setup Instructions

### Step 1 — Setup MySQL Database

1. Open **MySQL Workbench**
2. Connect to your local MySQL server
3. Open `schema.sql` → Run it (`Ctrl+Shift+Enter` or ⚡ button)
4. This creates database `credit_card_db` with all tables and a default admin user

### Step 2 — Download MySQL JDBC Connector

1. Go to: https://dev.mysql.com/downloads/connector/j/
2. Download the **Platform Independent** ZIP
3. Extract and copy `mysql-connector-j-x.x.x.jar`
4. Paste it into the `lib/` folder of this project

### Step 3 — Configure Database Password

Open `src/dao/DBConnection.java` and update your MySQL password:

```java
private static final String DB_PASSWORD = "root"; // ← change to your password
```

### Step 4 — Setup in Apache NetBeans

1. Open NetBeans → **File → New Project → Java with Existing Sources**
2. Set **Project Folder** to this directory
3. Add `src/` as the **Source Package Folder**
4. Right-click Project → **Properties → Libraries → Add JAR/Folder**
5. Browse to `lib/mysql-connector-j.jar` → Add it
6. Set **Main Class** to `ui.Main`
7. Press **F6** to Run

### Step 5 — (Alternative) Run from Command Line

```bash
# Compile
javac -cp lib/mysql-connector-j.jar -d out src/models/*.java src/dao/*.java src/services/*.java src/ui/*.java

# Run
java -cp out;lib/mysql-connector-j.jar ui.Main
```

> On Linux/macOS replace `;` with `:` in the classpath

---

## 🔑 Default Login Credentials

| Role | Username | Password |
|---|---|---|
| Admin | `admin` | `admin123` |

> ⚠️ Change the admin password after first login for security.

---

## 🖥️ Application Flow

```
🔐 Login / Register
        │
        ▼
┌───────────────────┐
│     Role Check    │
└───────────────────┘
     │           │
     ▼           ▼
👑 Admin      👤 Customer
  Menu          Menu
  │              │
  ├─ Issue Card  ├─ View Account
  ├─ Manage      ├─ Make Transaction
  │  Users       ├─ Pay Bill / EMI
  ├─ Reports     ├─ View History
  └─ Dashboard   └─ Security Settings
```

---

## 📚 Key Concepts Demonstrated

- ✅ **Layered Architecture** — Models → DAO → Services → UI separation of concerns
- ✅ **JDBC & MySQL** — Real database connectivity with prepared statements
- ✅ **DAO Design Pattern** — Clean data access abstraction for every entity
- ✅ **OOP Principles** — Encapsulation, Inheritance, Polymorphism across all layers
- ✅ **Exception Handling** — Graceful error management for DB and input failures
- ✅ **Security Features** — PIN, OTP, card lock/unlock mechanisms
- ✅ **Business Logic** — Interest calculation, EMI conversion, cash advance fees

---

## 🔮 Future Enhancements

- [ ] GUI using **Java Swing** or **JavaFX**
- [ ] REST API version using **Spring Boot**
- [ ] Export billing statements as **PDF**
- [ ] Email alerts for due dates and transactions
- [ ] Two-Factor Authentication (2FA)
- [ ] Docker support for easy deployment

---

## 👨‍💻 Developer

**Deepak Dubat**
B.Tech CSE (Cyber Security) | Jaipur National University

[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-blue?style=flat-square)](https://deepakdubat-portfolio.pages.dev/)
[![GitHub](https://img.shields.io/badge/GitHub-DeepakDubat-black?style=flat-square&logo=github)](https://github.com/DeepakDubat)
[![Email](https://img.shields.io/badge/Email-dubatdeepak3731@gmail.com-red?style=flat-square&logo=gmail)](mailto:dubatdeepak3731@gmail.com)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

> 💡 *Built as an academic project to demonstrate Java OOP, JDBC, DAO pattern, and MySQL-backed application development.*
