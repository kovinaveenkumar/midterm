# Advanced Python Calculator for Software Engineering Graduate Course

## Project Overview

This midterm assignment requires the development of an advanced Python-based calculator application. The project highlights professional software development practices such as:
- Clean and maintainable code
- Implementation of design patterns
- Comprehensive logging
- Dynamic configuration via environment variables
- Advanced data handling using Pandas
- Command-Line Interface (REPL) for real-time interaction

## Project Submission

- Create a **new GitHub repository** and ensure all work is committed with a clear history.
- Submit the **GitHub repository link** with proper documentation, configuration examples, and coherent commit history.
- Implement a **short description** explaining your use of design patterns, environment variables, and logging.
- Demonstrate your **exception handling** using both:
  - **LBYL** (Look Before You Leap)
  - **EAFP** (Easier to Ask for Forgiveness than Permission)
- Provide a **3-5 minute video** showcasing calculator functionality.
- Submit the repository link on **Canvas**.
- Ensure **GitHub Actions** are implemented, and the code passes **all tests**.

---

## Core Functionalities

### 1. Command-Line Interface (REPL)
The calculator application implements a **REPL (Read-Eval-Print Loop)**, which supports:
- **Basic arithmetic operations**: Addition, Subtraction, Multiplication, Division
- **Calculation history management**
- **Extended functionality through dynamically loaded plugins**

### 2. Plugin System
The application includes a **plugin system** to dynamically add new commands without modifying core logic. It supports:
- Loading plugins at runtime
- Listing all available commands in a **menu**

### 3. Calculation History Management with Pandas
Pandas is used to manage calculation history, allowing users to:
- Load, save, clear, and delete calculation history records from a **CSV file**.

### 4. Professional Logging Practices
Logging is implemented to track:
- **Application operations**, including errors and data manipulations
- **Log message severity levels** (INFO, WARNING, ERROR)
- **Dynamic logging configuration** via environment variables

### 5. Advanced Data Handling with Pandas
Pandas enables:
- Efficient data reading and writing to CSV files
- Managing historical calculations

---

## **Design Patterns for Scalable Architecture**
This project utilizes key **software design patterns** for maintainability and flexibility:

### 1. **Facade Pattern**
Provides a simplified interface for interacting with **Pandas-based history management**.

### 2. **Command Pattern**
Structures commands within the **REPL** for effective calculation and history management.

### 3. **Factory Method, Singleton, and Strategy Patterns**
These enhance the application’s structure, ensuring:
- **Flexibility**
- **Scalability**
- **Modular design**

---

## **Development, Testing, and Documentation Requirements**

### 1. **Testing and Code Quality**
- **90%+ test coverage** using **pytest**
- Enforces **PEP 8** standards with **pylint**

### 2. **Version Control Best Practices**
- Follows **logical commit history**
- Commits are grouped by feature development and corresponding tests

### 3. **Comprehensive Documentation**
The repository contains:
- **Setup instructions**
- **Usage examples**
- **Architectural decisions**
- **Design pattern justifications**
- **Logging strategy overview**

---

## **Installation & Setup Instructions**

### **1. Clone the Repository**
```sh
git clone https://github.com/YOUR_USERNAME/advanced-python-calculator.git
cd advanced-python-calculator
