# Midterm Assignment

## Demonstration Video
The demonstration video link is [here]() 

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


## Setup Instructions

1. **Clone the Repository:**  
   ```sh
   git clone git@github.com:kovinaveenkumar/midterm.git
   ```
2. **Navigate to the Project Directory:**  
   ```sh
   cd midterm
   ```
3. **Create a Python Virtual Environment:**  
   ```sh
   python -m venv venv
   ```
4. **Activate the Virtual Environment:**  
     ```sh
     source venv/bin/activate
     ```
5. **Install Dependencies:**  
   ```sh
   pip install -r requirements.txt
   ```
6. **Open the Code in VS Code:**  
   ```sh
   code .
   ```
7. **Run the Calculator Program:**  
   ```sh
   python3 main.py
   ```

## Running Tests

8. **Run Unit Tests:**  
   ```sh
   pytest
   ```
9. **Run Pyliny Test Output:**  
    ```sh
    pytest --pylint
    ```
10. **Check Test Coverage:**  
    ```sh
    pytest --cov
    ```
