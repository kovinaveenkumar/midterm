Advanced Python Calculator
Project Overview
This project implements an advanced Python-based calculator application designed to demonstrate professional software development practices. The calculator integrates clean, maintainable code, design patterns, comprehensive logging, dynamic configuration via environment variables, data handling with Pandas, and a command-line interface (REPL) for user interaction.
Features

Command-Line Interface (REPL): Interactive shell for performing calculations
Core Arithmetic Operations: Addition, subtraction, multiplication, and division
History Management with Pandas: Store, retrieve, and manipulate calculation history
Plugin System: Dynamically load new operations without modifying core code
Professional Logging: Detailed logging with configurable severity levels
Environment Variable Configuration: Dynamic application configuration
Robust Exception Handling: LBYL and EAFP principles for error management

Plugin System
The calculator features a flexible plugin system that allows for dynamic loading of operations without modifying the core application code. This system enables:

Dynamically loading and integrating plugins at runtime
Adding new operations without changing the main codebase
Accessing all available operations through a menu command

Core Operation Plugins
The calculator comes with these built-in operation plugins:

Add Plugin: Performs addition of two operands
Copyadd 5 3  # Result: 8

Subtract Plugin: Performs subtraction of two operands
Copysubtract 10 4  # Result: 6

Multiply Plugin: Performs multiplication of two operands
Copymultiply 6 7  # Result: 42

Divide Plugin: Performs division of two operands
Copydivide 20 5  # Result: 4


Control Commands
The REPL interface also supports these control commands:

Menu Command: Displays all available operations and commands
Copymenu  # Shows a list of all available commands

Exit Command: Terminates the calculator application
Copyexit  # Exits the application


Adding New Plugins
To create a new plugin:

Create a new Python file in the plugins directory
Define a class that implements the required interface
The plugin will be automatically discovered and loaded at runtime

Design Patterns Implemented
1. Factory Method Pattern
The Calculation class implements a factory method (create) that constructs and returns calculation objects, abstracting the creation process from the client code.
pythonCopy@staticmethod
def create(operand1: Decimal, operand2: Decimal, operation: Callable[[Decimal, Decimal], Decimal]):
    """Creates and returns a new Calculation object."""
    return Calculation(operand1, operand2, operation)
2. Command Pattern
Commands are implemented as classes with an execute method, encapsulating operations like history deletion:
pythonCopyclass DeleteHistoryCommand:
    """Command to delete a specific entry from the calculation history."""
    def execute(self, index):
        """Execute the delete command."""
        return ShowHistoryManager.delete_calculation(index)
3. Singleton Pattern
The Calculations class maintains a single history list shared across the application:
pythonCopyclass Calculations:
    """Manages the history of performed calculations."""
    history: List[Calculation] = []
Environment Variables
The application supports configuration through environment variables:

LOG_LEVEL: Sets the logging verbosity (DEBUG, INFO, WARNING, ERROR)
HISTORY_FILE: Specifies the location of the history CSV file

Logging Implementation
The application implements comprehensive logging that:

Records detailed application operations, data manipulations, errors, and informational messages
Differentiates log messages by severity (INFO, WARNING, ERROR)
Supports dynamic configuration through environment variables

Example of logging implementation:
pythonCopylogging.info("Deleted calculation at index %d: %s", index, deleted_row.to_dict())
Exception Handling
The calculator implements both "Look Before You Leap" (LBYL) and "Easier to Ask for Forgiveness than Permission" (EAFP) principles:
LBYL Example:
pythonCopyif operand2 == 0:
    raise ValueError("Cannot divide by zero.")
return operand1 / operand2
EAFP Example:
pythonCopytry:
    # Convert input strings to Decimal
    operand1_decimal, operand2_decimal = map(Decimal, [operand1, operand2])
    # ...
except InvalidOperation:
    print(f"Invalid number input: {operand1} or {operand2} is not a valid number.")
except ZeroDivisionError:
    print("Error: Division by zero is not allowed.")
Pandas Data Handling
The application uses Pandas DataFrames to:

Store calculation history in a structured format
Load and save history to CSV files
Provide efficient filtering and manipulation of historical data

Example:
pythonCopy@classmethod
def show_history(cls):
    """Display the calculation history in tabular form using Pandas."""
    cls.load_history()  # Load history before showing
    print("\nCalculation History:")
    if cls.history_df.empty:
        print("No history available.")
    else:
        print(cls.history_df)
Getting Started
Prerequisites

Python 3.8 or higher
Required packages (install via pip install -r requirements.txt):

pandas
pytest (for testing)
pylint (for code quality)



Installation

Clone the repository

bashCopygit clone https://github.com/yourusername/advanced-calculator.git
cd advanced-calculator

Install dependencies

bashCopypip install -r requirements.txt

Run the calculator

bashCopypython main.py
Basic Usage
Once the REPL is running, you can:
Calculation Commands

Addition: add 5 3 (Result: 8)
Subtraction: subtract 10 4 (Result: 6)
Multiplication: multiply 4 7 (Result: 28)
Division: divide 20 5 (Result: 4)

History Management

View calculation history: history
Clear all history: clear
Delete specific history entry: delete 2 (deletes entry at index 2)

System Commands

View available commands: menu or help
Exit the application: exit

Example session:
CopyWelcome to the Advanced Calculator!
Type 'menu' to see available commands or 'exit' to quit.

> add 10 5
The result of 10 add 5 is equal to 15

> multiply 4 3
The result of 4 multiply 3 is equal to 12

> history
Calculation History:
   Operation  Operand1  Operand2  Result
0        add        10         5      15
1   multiply         4         3      12

> exit
Goodbye!
Testing
The project includes comprehensive tests using pytest:
bashCopy# Run all tests
pytest

# Run tests with coverage report
pytest --cov=calculator
Project Structure
Copy├── app/
│   └── __init__.py
├── calculator/
│   ├── __init__.py
│   ├── calculation.py
│   ├── calculation_history.py
│   ├── calculations.py
│   └── operations.py
├── tests/
│   ├── __init__.py
│   ├── test_app.py
│   ├── test_calculation.py
│   ├── test_calculation_history.py
│   ├── test_calculations.py
│   ├── test_main.py
│   └── test_operations.py
├── logs/
│   └── app.log
├── .coveragerc
├── .gitignore
├── .pylintrc
├── logging.conf
├── main.py
├── pytest.ini
├── README.md
└── requirements.txt
