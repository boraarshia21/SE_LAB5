# 🧾 Inventory Management System

## 📖 Overview
This project implements a simple **Inventory Management System** in Python.  
It is designed to manage stock items — allowing users to add, remove, view, and check for low-stock products.  

The purpose of this lab was to **identify, analyze, and fix code quality and security issues** using **static analysis tools** such as:
- **Pylint**
- **Flake8**
- **Bandit**

Through these tools, several issues related to **coding style, maintainability, and security** were detected and resolved to improve overall code quality.

---

## ⚙️ Features
- Add new items to the inventory  
- Remove existing items from the inventory safely  
- Display the current stock report  
- Identify low-stock items below a threshold  
- Save and load inventory data to and from a JSON file  
- Handles exceptions safely and avoids insecure operations  

---

## 🧩 Tools Used

| Tool | Purpose | Example Issues Found |
|------|----------|----------------------|
| **Pylint** | Checks for code style, logical errors, and programming best practices | Missing docstrings, mutable default arguments, bare except |
| **Flake8** | Enforces PEP8 style guide compliance | Missing blank lines, unused imports |
| **Bandit** | Detects potential security flaws | Use of `eval()`, unsafe exception handling |

---

## 🛠️ Key Issues Identified & Fixed

### **Issue 1 — Missing Module and Function Docstrings**
- **Problem:** The original code lacked documentation, making it hard to understand.  
- **Fix:** Added clear module and function docstrings to explain purpose and behavior.

### **Issue 2 — Dangerous Default Argument (`logs=[]`)**
- **Problem:** Mutable default arguments can retain data between function calls.  
- **Fix:** Changed to `logs=None` and initialized inside the function to prevent shared state.

### **Issue 3 — Bare Except Statement**
- **Problem:** Using a generic `except:` hides real errors and makes debugging difficult.  
- **Fix:** Replaced with `except KeyError:` and added an informative print message.

### **Issue 4 — Unsafe File Handling**
- **Problem:** Files were opened using `open()` without a context manager, risking unclosed files.  
- **Fix:** Replaced with `with open(file, "r"/"w", encoding="utf-8") as f:` for automatic closing.

### **Issue 5 — Insecure Use of `eval()`**
- **Problem:** `eval()` can execute arbitrary code and is a major security risk.  
- **Fix:** Removed `eval()` and replaced with a simple print statement.

---

## 📈 Improvements After Fixes
- Improved **readability** through clear docstrings and spacing.
- Enhanced **security** by removing `eval()` and unsafe exception handling.
- Increased **robustness** using safer file operations.
- Better **maintainability** and **style compliance** (PEP8).

---

## 🚀 How to Run the Program

### **Requirements**
- Python 3.8 or higher

### **Steps**
1. Clone or open this project in your Codespace or local machine.  
2. Run the script using:
   ```bash
   python inventory_system.py

