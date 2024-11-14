# Module 6: Midterm Assessment – Enhancing the Python Calculator Application

## Module Overview

Welcome to **Module 6**, the midterm assessment for your Python programming course. This module serves as a comprehensive evaluation of the skills and knowledge you've acquired thus far, particularly focusing on **Object-Oriented Programming (OOP)**, **design patterns**, **data management** using `pandas`, **configuration management** with environment variables, **logging**, and **version control** using Git. The midterm project will require you to build upon the calculator command-line application developed in Module 5 by adding new features and functionalities as outlined below. This assessment is designed to accommodate a diverse range of skill levels, ensuring that both novice and experienced programmers can successfully complete the project while being challenged to demonstrate their proficiency.

## Learning Outcomes

By the end of this module, you will be able to:

1. **Utilize Git for version control and collaborative development.**
2. **Write and execute unit tests and integration tests for Python applications using Pytest.**
3. **Implement object-oriented programming principles in Python.**
4. **Create and manipulate CSV files using Python and the `pandas` library.**
5. **Apply professional programming techniques such as DRY and error handling using LBYL and EAFP.**
6. **Develop a command-line application using the REPL pattern.**
7. **Implement design patterns such as Factory, Observer, Strategy, Singleton, and Memento to enhance code scalability and maintainability.**
8. **Implement comprehensive logging strategies to monitor and debug applications.**
9. **Apply professional terminology and concepts related to web systems development.**
10. **Set up GitHub Actions for Continuous Integration (CI), automating the execution of tests to demonstrate DevOps principles to ensure software quality.**

## Learning Pathway

### Read

Your **primary textbook** for this module is the provided codebase from Module 5. Each `.py` file within the `app/` directory contains the relevant code for the calculator application, including OOP principles, design patterns, error handling, data management with `pandas`, configuration management using environment variables, logging, and version control implementation.

### Watch

See Canvas for uploaded instructional videos that cover advanced OOP concepts, design patterns, unit testing with Pytest, logging strategies, and best practices in Git version control.

### Review

Utilize the following cheat sheets as quick references to aid your study and project development:

1. **[Advanced OOP Cheat Sheet](https://realpython.com/python-cheat-sheet/)**
   - **Purpose:** Offers a quick reference for advanced OOP concepts and syntax in Python.

2. **[Design Patterns Cheat Sheet](https://refactoring.guru/design-patterns)**
   - **Purpose:** Provides essential information on various design patterns, including Factory, Observer, Strategy, Singleton, and Memento.

3. **[pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)**
   - **Purpose:** Quick reference for using `pandas` for data manipulation and analysis.

4. **[CSV Handling Cheat Sheet](https://realpython.com/python-csv/)**
   - **Purpose:** Comprehensive guide to reading from and writing to `CSV` files in Python using `pandas` and the built-in `csv` module.

5. **[Test Coverage Cheat Sheet](https://pytest-cov.readthedocs.io/en/latest/)**
   - **Purpose:** Quick reference for measuring and managing test coverage in Python projects.

6. **[Python Logging Cheat Sheet](https://realpython.com/python-logging/)**
   - **Purpose:** Quick reference for implementing and configuring logging in Python applications.

7. **[Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)**
   - **Purpose:** Quick reference for essential Git commands and workflows.

8. **[python-dotenv Documentation](https://saurabh-kumar.com/python-dotenv/)**
   - **Purpose:** Guide on loading environment variables from `.env` files into Python applications.

## Submit

**Activity Type:** Advanced Hands-on Assignment  

**Activity Title:** Midterm Project – Enhanced Calculator Command-Line Application  

**Grading Type:** Points  

**Submission Instructions:** Submit a link to your GitHub repository containing the project and complete the midterm test on Canvas.

### Instructions

#### Repository Setup:

- **Initialize Git Repository:**
  - Ensure your Git repository is properly initialized and pushed to GitHub.
  - **Directory Structure:** Organize your project with a well-structured directory layout as follows:
    ```
    project_root/
    ├── app/
    │   ├── __init__.py
    │   ├── calculator.py
    │   ├── calculation.py
    │   ├── calculator_config.py
    │   ├── calculator_memento.py
    │   ├── exceptions.py
    │   ├── history.py
    │   ├── input_validators.py
    │   ├── operations.py
    │   └── logger.py
    ├── tests/
    │   ├── __init__.py
    │   ├── test_calculator.py
    │   ├── test_calculation.py
    │   ├── test_operations.py
    │   └── ...
    ├── .env
    ├── requirements.txt
    ├── README.md
    └── .github/
        └── workflows/
            └── python-app.yml
    ```

- **Virtual Environment:**
  - Create and activate a virtual environment for your project.
  - Example using `venv`:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

- **Install Dependencies:**
  - Ensure all necessary packages are listed in `requirements.txt`.
  - Install dependencies using:
    ```bash
    pip install -r requirements.txt
    ```

- **Git Usage:** 
  - Commit your changes regularly with clear and descriptive commit messages to track your progress.
  - Use branches for feature development if necessary.
  - Ensure that your Git history reflects the development process, which will be part of your grade.
  - **IMPORTANT:** **YOU MUST HAVE A CLEAR COMMIT HISTORY OF YOUR PROGRESS. PROJECTS WITHOUT A CLEAR COMMIT HISTORY AS JUDGED BY THE INSTRUCTOR WILL BE FLAGGED AS A POSSIBLE ACADEMIC INTEGRITY VIOLATION**

#### Application Development:

Enhance the calculator application with the following features:

1. **Additional Arithmetic Operations:**
   - **Mandatory Operations:**
     - **Power:** Raise one number to the power of another.
     - **Root:** Calculate the nth root of a number.
     - **Modulus:** Compute the remainder of the division of two numbers.
     - **Integer Division:** Perform division that results in an integer quotient, discarding any fractional part.
   - **Implementation Details:**
     - Utilize the **Factory Design Pattern** to manage the creation of different operation instances.
     - Ensure that each operation takes exactly two numerical inputs and returns the correct result.
     - Handle invalid operations gracefully with appropriate error messages.

2. **History Management with Undo/Redo:**
   - Implement **Undo** and **Redo** functionalities using the **Memento Design Pattern**.
   - Allow users to revert the last calculation or redo an undone calculation.
   - Ensure that the history stack accurately reflects the state after each operation.

3. **Observer Pattern for Logging and Auto-Save:**
   - Implement the **Observer Design Pattern** to allow observers to respond to new calculations.
   - **Observers to Implement:**
     - **LoggingObserver:** Logs each calculation with details (operation, operands, result) to a log file.
     - **AutoSaveObserver:** Automatically saves the calculation history to a CSV file using `pandas` whenever a new calculation is performed.
   - Ensure that observers are registered with the Calculator and respond appropriately to events.

4. **Configuration Management:**
   - Manage configuration settings using a `.env` file and the `python-dotenv` package.
   - **Configuration Parameters:**
     - **Base Directories:**
       - `CALCULATOR_BASE_DIR`: Base directory for the calculator.
       - `CALCULATOR_LOG_DIR`: Directory for log files.
       - `CALCULATOR_HISTORY_DIR`: Directory for history files.
     - **History Settings:**
       - `CALCULATOR_MAX_HISTORY_SIZE`: Maximum number of history entries.
       - `CALCULATOR_AUTO_SAVE`: Whether to auto-save history (`true` or `false`).
     - **Calculation Settings:**
       - `CALCULATOR_PRECISION`: Number of decimal places for calculations.
       - `CALCULATOR_MAX_INPUT_VALUE`: Maximum allowed input value.
       - `CALCULATOR_DEFAULT_ENCODING`: Default encoding for file operations.
   - **Implementation Details:**
     - Use `python-dotenv` to load environment variables from the `.env` file.
     - Ensure that the application can load and validate these configurations on startup.
     - Provide default values for configurations if environment variables are not set.

5. **Error Handling and Input Validation:**
   - Implement robust error handling using custom exceptions (`OperationError`, `ValidationError`, etc.).
   - Validate user inputs to ensure they are numerical and within allowed ranges.
   - Use `pandas` to manage data-related errors, such as issues with reading or writing CSV files.
   - Provide meaningful error messages to guide the user in correcting their input.

6. **Logging:**
   - Implement comprehensive logging strategies using Python’s `logging` module.
   - Log important events, errors, and calculation details with appropriate logging levels (INFO, WARNING, ERROR).
   - Configure logging to write to a file specified in the configuration (`CALCULATOR_LOG_FILE`).
   - Ensure that all new operations are logged appropriately using the existing `Logger` class.

7. **Command-Line Interface (REPL):**
   - Develop a user-friendly command-line interface using the **Read-Eval-Print Loop (REPL)** pattern.
   - **Supported Commands:**
     - `add`, `subtract`, `multiply`, `divide`, `power`, `root`, `modulus`, `int_divide` – Perform calculations.
     - `history` – Display calculation history.
     - `clear` – Clear calculation history.
     - `undo` – Undo the last calculation.
     - `redo` – Redo the last undone calculation.
     - `save` – Manually save calculation history to file using `pandas`.
     - `load` – Load calculation history from file using `pandas`.
     - `help` – Display available commands.
     - `exit` – Exit the application gracefully.

8. **Unit Testing:**
   - Write comprehensive unit tests using `pytest` for all new functionalities.
   - Cover typical use cases and edge cases (e.g., division by zero, negative exponents).
   - Implement parameterized tests to efficiently cover multiple scenarios.
   - Achieve **90% Test Coverage or Better** using tools like `pytest-cov`.
   - **Handling Coverage Exceptions:** Use coverage comments (e.g., `# pragma: no cover`) for lines that are intentionally excluded from coverage metrics.

9. **Serialization and Data Persistence:**
   - **Saving History:**
     - Use `pandas` to serialize calculation history to a CSV file.
     - Implement a method to convert the history (a list of `Calculation` instances) into a pandas DataFrame and save it to the file specified in the configuration (`CALCULATOR_HISTORY_FILE`).
     - Ensure that the CSV file includes columns for operation, operands, result, and timestamp.
   - **Loading History:**
     - Use `pandas` to deserialize calculation history from a CSV file.
     - Implement a method to read the CSV file into a pandas DataFrame and convert each row back into a `Calculation` instance.
     - Handle cases where the CSV file does not exist or is malformed gracefully, providing appropriate error messages.

10. **GitHub Actions for Continuous Integration (CI):**
    - Set up GitHub Actions to automatically run your tests and measure test coverage on each push or pull request to the `main` branch.
    - **Workflow Requirements:**
      - **Check Out Code:** Use `actions/checkout` to access the repository.
      - **Set Up Python Environment:** Use `actions/setup-python` to specify the Python version.
      - **Install Dependencies:** Install all required packages from `requirements.txt`.
      - **Run Tests:** Execute `pytest` with coverage measurement using `pytest-cov`.
      - **Enforce Coverage Threshold:** Ensure that the CI pipeline fails if test coverage falls below **90%**.
    - **Example Workflow File (`.github/workflows/python-app.yml`):**
      ```yaml
      name: Python application

      on:
        push:
          branches:
            - main  # Run tests on any push to the main branch
        pull_request:
          branches:
            - main  # Run tests on any pull request to the main branch

      jobs:
        test:
          runs-on: ubuntu-latest

          steps:
            - name: Check out the code
              uses: actions/checkout@v3

            - name: Set up Python
              uses: actions/setup-python@v4
              with:
                python-version: '3.x'  # Set your desired Python version

            - name: Install dependencies from requirements.txt
              run: |
                python -m pip install --upgrade pip
                pip install -r requirements.txt
                pip install pytest pytest-cov  # Ensure pytest-cov is installed

            - name: Run tests with pytest and enforce 90% coverage
              run: |
                pytest --cov=app --cov-fail-under=90
      ```
    - **Handling Coverage Exceptions:** In your code, add comments like `# pragma: no cover` to lines that are intentionally excluded from coverage metrics (e.g., lines with `pass` or `continue`). This ensures that your coverage report accurately reflects the test coverage without being penalized for these lines.
      ```python
      if some_condition:
          pass  # pragma: no cover
      ```

11. **Documentation:**
    - Create a detailed `README.md` file with setup and usage instructions.
    - **README.md Should Include:**
      - **Project Description:** Overview of the calculator application and its features.
      - **Installation Instructions:** Steps to set up the virtual environment and install dependencies.
      - **Configuration Setup:** Instructions on creating and configuring the `.env` file with necessary environment variables.
      - **Usage Guide:** Detailed explanation of how to use the command-line interface and its supported commands.
      - **Testing Instructions:** How to run unit tests and check test coverage.
      - **CI/CD Information:** Overview of GitHub Actions workflow and its purpose.
    - Document your code with meaningful comments and docstrings to enhance readability and maintainability.
    - Include instructions on setting up `.env` files and configuring logging.

#### Best Practices:

- **DRY Principle:** Apply the DRY (Don't Repeat Yourself) principle and other best practices to ensure your code is maintainable and efficient.
- **Modular Design:** Organize your code into modules and classes to enhance readability and reusability.
- **Logging:** Ensure that all new operations are logged appropriately using the existing `Logger` class.

#### Optional Features (For Advanced Students - AT LEAST ONE OF THESE IS REQUIRED FOR AN A):

1. **Dynamic Help Menu:**
   - Implement the **Decorator Design Pattern** to dynamically generate the help menu based on the available operations.
   - Ensure that adding new operations automatically updates the help menu without manual changes.
   - **Tutorial Link:** [Decorator Design Pattern in Python](https://refactoring.guru/design-patterns/decorator/python/example)

2. **Color-Coded Outputs:**
   - Add color-coded outputs to improve the readability and user experience of the application.
   - **Tutorial Link:** [Colorama Library Tutorial](https://realpython.com/python-coloring-terminal-output/)

3. **Additional Design Patterns:**
   - Incorporate the **Command Design Pattern** to encapsulate requests as objects, allowing for parameterization and queuing of operations.
   - **Tutorial Link:** [Command Pattern in Python](https://refactoring.guru/design-patterns/command/python/example)

## Grading Rubric

Your midterm project will be evaluated based on the following criteria:

| **Category**                      | **Excellent (90-100%)**                                                                                                                                                                | **Good (75-89%)**                                                                                                                                                  | **Satisfactory (60-74%)**                                                                                                                            | **Needs Improvement (<60%)**                                                                                               | **Points** |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|------------|
| **Functionality**                 | All mandatory features are fully implemented and function correctly. Optional features are also implemented successfully.                                                            | All mandatory features are implemented and function correctly. Most optional features are implemented.                                                            | Most mandatory features are implemented with minor issues. Few optional features are implemented.                                                    | Several mandatory features are missing or do not function correctly. Optional features are not implemented.                  | /40        |
| **Code Quality**                  | Code is clean, well-organized, and follows best practices. Proper use of OOP principles and design patterns. Code is free of unnecessary complexity and duplication.                     | Code is organized and follows best practices. Good use of OOP principles and design patterns with minor issues.                                                          | Code follows some best practices but may have areas of improvement. Use of OOP principles and design patterns is inconsistent.                        | Code is disorganized, difficult to read, and does not follow best practices. Poor use of OOP principles and design patterns. | /20        |
| **Unit Testing at least 90%**                  | Comprehensive unit tests covering all new features, including edge cases. All tests pass successfully.                                                                                | Good coverage of unit tests for new features with most edge cases handled. All tests pass successfully.                                                             | Basic unit tests are present but lack coverage for edge cases. Some tests may fail or have issues.                                                   | Inadequate or missing unit tests. Many tests fail or do not cover new features effectively.                                   | /15        |
| **Error Handling**                | Robust error handling for all new features. The application gracefully manages invalid inputs and unexpected scenarios without crashing.                                               | Good error handling with minor issues. Most invalid inputs and unexpected scenarios are managed gracefully.                                                        | Basic error handling is implemented but may not cover all invalid inputs or unexpected scenarios.                                                   | Inadequate error handling. The application crashes or behaves unpredictably with invalid inputs or unexpected scenarios.       | /10        |
| **Logging Implementation**        | Logging is comprehensive and effectively records all new operations with detailed information. Proper use of logging levels and log management (if optional features implemented).       | Logging covers all new operations with sufficient detail. Proper use of logging levels.                                                                           | Basic logging is implemented but may lack detail or miss some new operations.                                                                      | Inadequate or missing logging for new operations. Logs lack useful information or are not properly managed.                    | /10        |
| **Documentation**                 | Clear and thorough documentation. `README.md` includes detailed instructions on using new features. Additional documentation explains code enhancements effectively.                      | Good documentation. `README.md` includes instructions on new features. Additional documentation covers most code enhancements.                                       | Basic documentation is present but may lack detail. `README.md` includes some instructions on new features.                                           | Inadequate or missing documentation. `README.md` lacks instructions or does not explain new features effectively.              | /5         |
| **Git Utilization**               | Exemplary use of Git for version control and collaborative development. Commit history is clear, descriptive, and reflects the development process. Branching and merging are handled effectively. | Good use of Git for version control and collaborative development. Commit messages are descriptive and reflect the development process. Minor issues with branching or merging. | Basic use of Git for version control. Commit messages are somewhat descriptive. Limited use of branching or merging.                                 | Inadequate use of Git for version control. Commit history is unclear or lacks descriptive messages.                               | /10        |
| **Optional Features Implementation** | All optional features are fully implemented and function correctly, enhancing the application significantly.                                                                            | Most optional features are implemented and function correctly, adding noticeable improvements to the application.                                                 | Some optional features are implemented with minor issues, providing limited enhancements to the application.                                         | Few or no optional features are implemented, with little to no impact on the application's functionality.                      | /10        |
| **Total**                          |                                                                                                                                                                                        |                                                                                                                                                                    |                                                                                                                                                       |                                                                                                                            | /100       |

## Reflect

**Title:** Module 6 In-Depth Reflection  
**Grading Type:** Points  
**Instructions:**
- **Reflection Essay:** Compose a comprehensive reflection (300-400 words) on your experience enhancing the professional calculator command-line application.
  - **Application of Concepts:** Analyze how the additional arithmetic operations, undo/redo functionality, design patterns, data management with `pandas`, configuration management using environment variables, logging, and Git version control learned in this module can be applied to real-world programming scenarios.
  - **Challenges and Solutions:** Discuss any challenges you encountered during the project, particularly in implementing design patterns, adding new operations, handling data persistence with `pandas`, managing configurations with environment variables, ensuring comprehensive testing, or effectively using Git for version control, and the strategies you used to overcome them.
  - **Self-Evaluation:** Evaluate your current level of confidence in using Git for version control, writing and executing unit tests with Pytest, implementing advanced OOP principles and design patterns, managing data with CSV files using `pandas`, applying professional programming techniques, and implementing logging. Identify areas where you feel proficient and areas where you need further practice or support.
- **Purpose:** This activity aims to encourage deep metacognition and help you connect new knowledge with prior experiences and future applications.

## Midterm Test

**Title:** Midterm Test – Python Calculator Application Enhancement  
**Grading Type:** Points  
**Instructions:**
- **Midterm Test:** Complete the midterm test on Canvas as specified by your instructor.
  - The test will assess your understanding of the concepts applied in enhancing the calculator application, including OOP principles, design patterns, data management with `pandas`, configuration management using environment variables, logging, unit testing, and Git version control.
  - **Question Types:** The test may include multiple-choice, short answer, and code analysis questions to thoroughly evaluate your comprehension and application of the module's content.
- **Preparation:** 
  - Review all provided materials, including the codebase, supplementary articles, instructional videos, and cheat sheets.
  - Ensure you understand how to implement and test advanced OOP concepts and design patterns.
  - Familiarize yourself with using `pandas` for data management, managing configurations with environment variables, implementing logging, writing unit tests with Pytest, and effectively using Git for version control.

## Watch

See Canvas for uploaded instructional videos that cover advanced OOP concepts, design patterns, unit testing with Pytest, logging strategies, and best practices in Git version control.

## Read

Your **primary textbook** for this module is the provided codebase from Module 5. Each `.py` file within the `app/` directory contains the relevant code for the calculator application, including OOP principles, design patterns, error handling, data management with `pandas`, configuration management using environment variables, logging, and version control implementation.

## Supplementary Articles

To enhance your understanding of the codebase, please refer to the following Python documentation and resources:

- **Object-Oriented Programming:**
  - [Python Data Classes](https://docs.python.org/3/library/dataclasses.html): Understand how to use data classes to simplify class definitions and manage data attributes efficiently.
  - [Python Properties](https://docs.python.org/3/library/functions.html#property): Learn how to use `@property` decorators to create managed attributes in your classes.
  - [Python Abstract Base Classes (ABC)](https://docs.python.org/3/library/abc.html): Explore how to define abstract base classes to create interfaces for your classes.

- **Design Patterns:**
  - [Strategy Design Pattern](https://refactoring.guru/design-patterns/strategy): Understand and implement the Strategy design pattern to define a family of algorithms.
  - [Factory Method Design Pattern](https://refactoring.guru/design-patterns/factory-method): Learn how to implement the Factory design pattern to manage object creation.
  - [Observer Design Pattern](https://refactoring.guru/design-patterns/observer): Implement the Observer design pattern to allow objects to subscribe and react to events.
  - [Singleton Design Pattern](https://refactoring.guru/design-patterns/singleton): Learn how to implement the Singleton pattern to ensure a class has only one instance.
  - [Memento Design Pattern](https://refactoring.guru/design-patterns/memento): Gain a deeper understanding of how the Memento pattern can be used to capture and restore an object's state.
  - [Decorator Design Pattern](https://refactoring.guru/design-patterns/decorator): Learn how to implement the Decorator pattern to add responsibilities to objects dynamically.

- **Data Management:**
  - [pandas Documentation](https://pandas.pydata.org/docs/): Master data manipulation and analysis using the pandas library.
  - [Handling CSV Files in Python](https://docs.python.org/3/library/csv.html): Learn how to read from and write to CSV files using Python's built-in `csv` module.
  - **Usage of pandas in Calculator:**
    - [Real Python: Working with CSV Files in Python using pandas](https://realpython.com/python-pandas-read-write-files/): Practical guide on using `pandas` for reading and writing CSV files, which is essential for managing calculation history.

- **Configuration Management:**
  - [python-dotenv Documentation](https://saurabh-kumar.com/python-dotenv/): Learn how to load environment variables from `.env` files into your Python applications.
  - [Managing Secrets in Git](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-security-hardening-for-git): Best practices for keeping sensitive data out of version control.

- **Logging:**
  - [Python Logging Module](https://docs.python.org/3/library/logging.html): Implement logging in your applications to track events, errors, and debug information.
  - [Real Python: Logging in Python](https://realpython.com/python-logging/): A comprehensive guide to implementing and configuring logging in Python applications.

- **Testing and Coverage:**
  - [Achieving 90%+ Test Coverage in Python](https://pytest-cov.readthedocs.io/en/latest/): Use coverage tools with pytest to measure and achieve full test coverage.

- **Version Control:**
  - [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf): Quick reference for essential Git commands and workflows.
  - [GitHub Actions Documentation](https://docs.github.com/en/actions): Learn how to set up and use GitHub Actions for Continuous Integration.

## Tips for Success

- **Manage Your Time:** Allocate sufficient time to plan, implement, test, and document your enhancements.
- **Focus on Quality:** Prioritize writing clean, maintainable code over adding numerous features.
- **Leverage Design Patterns:** Utilize the design patterns learned to structure your enhancements effectively.
- **Write Comprehensive Tests:** Ensure that your unit tests cover a wide range of scenarios, including edge cases.
- **Utilize Git Effectively:** Regularly commit your work with descriptive messages. Use branches for feature development to maintain a clean main branch.
- **Leverage pandas for Data Management:** Use `pandas` to efficiently handle calculation history, making data manipulation and persistence straightforward.
- **Manage Configurations with Environment Variables:** Use environment variables to manage configuration settings securely and flexibly.
- **Seek Help When Needed:** If you encounter challenges, refer to the supplementary articles or reach out to your instructors for guidance.

## Submission Deadline

Please ensure that your GitHub repository link and completion of the midterm test on Canvas are submitted by **[Insert Deadline Here]**. Late submissions may be subject to grade penalties as per the course policy.

---

**Good luck with your midterm assessment!** Demonstrate your understanding and proficiency by thoughtfully enhancing the calculator application, showcasing the skills you've developed throughout the course.

---

## Appendix: Provided Code Functionalities

To ensure clarity on the functionalities you are expected to implement, here is an overview of the key components from the provided codebase:

### 1. Calculation Model (`calculation.py`)

- **Purpose:** Represents a single calculation, encapsulating operation details, operands, result, and timestamp.
- **Features:**
  - Supports operations: Addition, Subtraction, Multiplication, Division, Power, Root.
  - Methods for performing calculations, serializing to/from dictionaries.
  - Handles errors like division by zero and invalid operations.

### 2. Calculator Configuration (`calculator_config.py`)

- **Purpose:** Manages configuration settings using environment variables.
- **Features:**
  - Configurable parameters: directories, history size, auto-save, precision, input limits, encoding.
  - Methods to validate configurations.
  - Utilizes `python-dotenv` to load environment variables from a `.env` file.

### 3. Calculator Memento (`calculator_memento.py`)

- **Purpose:** Implements the Memento Design Pattern for undo/redo functionality.
- **Features:**
  - Stores the history of calculations.
  - Methods to serialize/deserialize mementos.

### 4. Calculator Class (`calculator.py`)

- **Purpose:** Core class managing operations, history, observers, and configuration.
- **Features:**
  - Implements Strategy, Factory, Observer, and Memento Design Patterns.
  - Methods for performing operations, managing history, undo/redo, saving/loading history using `pandas`.
  - Observer registration and notification.
  - Handles configuration settings loaded from environment variables.

### 5. Exception Hierarchy (`exceptions.py`)

- **Purpose:** Custom exceptions for error handling.
- **Classes:**
  - `CalculatorError`: Base class.
  - `ValidationError`: Input validation failures.
  - `OperationError`: Calculation execution failures.
  - `ConfigurationError`: Configuration issues.

### 6. History Management (`history.py`)

- **Purpose:** Implements the Observer Design Pattern for logging and auto-saving.
- **Classes:**
  - `HistoryObserver` (Abstract Base Class)
  - `LoggingObserver`: Logs calculations to a file.
  - `AutoSaveObserver`: Automatically saves history based on configuration using `pandas`.

### 7. Input Validation (`input_validators.py`)

- **Purpose:** Validates and sanitizes user inputs.
- **Features:**
  - Validates numerical inputs against configuration constraints.
  - Converts inputs to `Decimal` type.
  - Utilizes `pandas` to manage data-related errors during saving/loading.

### 8. Operation Classes (`operations.py`)

- **Purpose:** Implements various arithmetic operations using the Strategy Design Pattern.
- **Classes:**
  - `Operation` (Abstract Base Class)
  - `Addition`, `Subtraction`, `Multiplication`, `Division`, `Power`, `Root`, `Modulus`, `IntegerDivision`: Concrete implementations.
  - `OperationFactory`: Factory class to create operation instances based on operation type.

### 9. Calculator REPL (`calculator_repl.py`)

- **Purpose:** Provides a command-line interface for user interaction.
- **Features:**
  - Processes user commands and interacts with the `Calculator` class.
  - Supports commands like `add`, `subtract`, `multiply`, `divide`, `power`, `root`, `modulus`, `int_divide`, `history`, `undo`, `redo`, `save`, `load`, `help`, `exit`.
  - Handles user input, displays results, and manages application flow.

### 10. GitHub Actions Workflow (`.github/workflows/python-app.yml`)

- **Purpose:** Automates testing and coverage checks on each push or pull request.
- **Features:**
  - Checks out code, sets up Python environment, installs dependencies.
  - Runs tests with `pytest` and enforces a minimum coverage threshold.

---

**Note:** Ensure that your project aligns with the provided code functionalities and adheres to best practices in software development. Utilize the supplementary articles and instructional materials to guide your implementation and enhance your understanding of the concepts involved.

Good luck, and we look forward to seeing your enhanced Python Calculator Application!