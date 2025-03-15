# Midterm Assignment

## Overview
This repository contains the code and resources for the midterm assignment. It includes a calculator application implemented in Python, along with necessary configurations, test cases, and logging mechanisms.

## Project Structure
```
midterm/
│── app/                     # Application logic
│── calculator/              # Core calculator functions
│── logs/                    # Log files for debugging
│── tests/                   # Unit tests
│── main.py                  # Entry point of the application
│── requirements.txt         # Dependencies for the project
│── README.md                # Project documentation
│── pytest.ini               # Pytest configuration
│── logging.conf             # Logging configuration
│── calculation_history.csv  # Stored calculation history
│── .gitignore               # Git ignore file
│── .pylintrc                # Pylint configuration
│── .coverage                # Coverage reports
│── .pytest_cache/           # Pytest cache
│── .github/                 # GitHub workflow configurations
│── __pycache__/             # Python cache files
```


## Features
- **Command-Line Interface (REPL)**: Interactive mode for executing operations.
- **Calculation History**: Stores, retrieves, and clears previous calculations.
- **Plugin System**: Allows adding new features dynamically without modifying the core code.
- **Logging System**: Records errors, warnings, and application events for debugging.
- **Data Handling with Pandas**: Manages history records and saves them as CSV files.
- **Exception Handling**: Implements try/except mechanisms for handling runtime errors.
- **Design Patterns**: Uses Facade, Command, and Strategy patterns for a scalable structure.
