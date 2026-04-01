# 📚 Library Management System

A feature-rich, console-based Library Management System built in Java. It supports multi-role staff authentication, book tracking, member registration, and full transaction logging — all within a beautifully styled terminal UI using ANSI colour codes.

---

## ✨ Features

- **Secure Staff Login** — Role-based access for Admins, Librarians, and Clerks
- **Admin Setup on First Launch** — Interactive admin account creation at startup
- **Book Inventory** — Pre-loaded catalogue with real-time availability tracking
- **Member Management** — Auto-registers new members on first book issue
- **Issue & Return Workflow** — Full transaction lifecycle with timestamps
- **Transaction History** — View all active issues and a complete audit log
- **Staff Directory** — Browse registered staff and their roles
- **Colourful Terminal UI** — ANSI-styled tables, banners, dividers, and status indicators

---

## 🛠️ Tech Stack

| Layer | Details |
|---|---|
| Language | Java 17+ |
| I/O | `java.util.Scanner` (console) |
| Date/Time | `java.time.LocalDateTime` |
| Storage | In-memory (`ArrayList`) |
| UI | ANSI escape codes |

---

## 🚀 Getting Started

### Prerequisites

- Java 17 or higher installed
- A terminal that supports ANSI colour codes (Linux/macOS Terminal, Windows Terminal, Git Bash)

### Compile

```bash
javac LibraryManagementSystem.java
```

### Run

```bash
java LibraryManagementSystem
```

---

## 🔐 First-Time Setup

On first launch, you will be prompted to create the Admin account:

```
  ╔══════════════════════════════════════════════════════════╗
  ║          📚 LIBRARY MANAGEMENT SYSTEM.📚                ║
  ║              Powered by Java Console                     ║
  ╚══════════════════════════════════════════════════════════╝

===== SETUP ADMIN ACCOUNT =====
Enter Admin ID: admin01
Enter Admin Name: Alice Smith
Set Admin Password: ********

  ▌ Staff Login
  ────────────────────────────────────────────────────────────
  ➤ Staff ID: ST-12
  ➤ Password: ******

  ✔ Welcome back, John Doe [ADMIN]
```

This account is used to log in and access all administrative functions.

---

## 🗂️ Project Structure

```
LibraryManagementSystem.java
│
├── Book                  — Book model (ID, title, author, availability)
├── Staff                 — Staff model (ID, name, role, password)
├── Member                — Member model (ID, name, contact)
├── BookTransaction       — Transaction model (issue/return records)
│
└── LibraryManagementSystem (main)
    ├── seedData()        — Bootstrap: admin setup + sample books
    ├── loginScreen()     — Staff authentication
    ├── mainMenu()        — Top-level navigation
    ├── adminMenu()       — Administrative functions
    ├── addStaff()        — Add Clerk or Librarian
    ├── issueBook()       — Issue a book to a member
    ├── returnBook()      — Return a book by transaction ID
    ├── viewAllBooks()    — Display full book catalogue
    ├── viewIssuedHistory()— Active issued books
    └── viewMembersAndLogs()— Members, staff, and transaction log
```

---

## 🧭 Navigation Overview

```
Login
 └── Main Menu
      ├── [1] Administrative Functions
      │     ├── Add Clerk
      │     ├── Add Librarian
      │     ├── View Issued Books History
      │     ├── View All Books
      │     ├── Issue / Return Book
      │     └── Logout
      ├── [2] View Members & Logs
      │     ├── Staff Directory
      │     ├── Registered Members
      │     └── Full Transaction Log
      └── [3] Exit
```

---

## 📖 Sample Books (Pre-loaded)

| Book ID | Title | Author |
|---|---|---|
| BK-201 | Clean Code | Robert C. Martin |
| BK-202 | The Pragmatic Programmer | David Thomas |
| BK-203 | Design Patterns | Gang of Four |
| BK-204 | Effective Java | Joshua Bloch |
| BK-205 | Introduction to Algorithms | CLRS |

---

## 👥 Staff Roles

| Role | Capabilities |
|---|---|
| `ADMIN` | Full access — add staff, issue/return books, view all records |
| `LIBRARIAN` | Manage books and members |
| `CLERK` | Assist with issue/return operations |

> **Note:** Role-based permission enforcement can be added as a future enhancement.

---

## 📋 Transaction Flow

1. Staff logs in with ID and password
2. Navigate to **Issue / Return Book**
3. **Issue:** Enter member name + contact → select book by ID → transaction created
4. **Return:** Enter transaction ID → book marked available, return date stamped
5. All transactions are visible in the **Full Transaction Log**

---

## 🔮 Possible Enhancements

- [ ] Persist data to file or database (JSON / SQLite)
- [ ] Enforce role-based access control per menu
- [ ] Add due dates and overdue fine calculation
- [ ] Book search by title or author
- [ ] Password hashing (e.g. BCrypt)
- [ ] Export reports to CSV

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
