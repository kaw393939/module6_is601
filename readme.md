
# **Module 6: Mid-Term Project - Advanced Calculator Application**

## **Module Overview**

Welcome to **Module 6**, the mid-term project segment of your Python programming course. In this module, you will apply the concepts and skills you've acquired thus far by developing an **Advanced Calculator Application**. This project is designed to accommodate a wide variety of students by offering two tiers of complexity: a **Basic Calculator** for those aiming for a **B** grade and an **Enhanced Calculator** for those striving for an **A** grade.

Your primary objective is to design, implement, and thoroughly test a calculator application that demonstrates your understanding of advanced software design principles, design patterns, data management with `pandas`, and comprehensive testing methodologies. Additionally, both project tiers emphasize the integration of `pandas` for efficient data handling and `logging` for robust event tracking, ensuring that all students gain experience with these essential tools.

## **Learning Outcomes**

By the end of this module, you will be able to:

- **Design and Implement Software Applications:** Apply advanced design patterns to create scalable and maintainable Python applications.
- **Data Management with pandas:** Utilize the `pandas` library for efficient data handling, storage, and retrieval.
- **Logging for Event Tracking:** Implement logging to monitor application behavior and debug issues effectively.
- **Testing and Quality Assurance:** Develop comprehensive unit and parameterized tests to ensure code reliability, achieving high test coverage.
- **Continuous Integration (CI):** Configure GitHub Actions to automate testing and enforce code quality standards.
- **Documentation and Best Practices:** Maintain clean, well-documented, and modular code adhering to best coding practices.
- **Maintain Academic Integrity:** Understand and adhere to academic integrity policies, ensuring original work and proper version control practices.

## **Project Overview**

You are tasked with creating a **Calculator Application** that can perform various arithmetic operations. The project is divided into two tiers to accommodate different skill levels:

1. **Basic Calculator (Grade B)**
2. **Enhanced Calculator (Grade A)**

### **1. Basic Calculator (Grade B)**

**Objective:** Develop a functional calculator that performs basic arithmetic operations with a user-friendly command-line interface (CLI).

**Requirements:**

- **Supported Operations:**
  - Addition
  - Subtraction
  - Multiplication
  - Division

- **Features:**
  - **REPL Interface:** Implement a Read-Eval-Print Loop for continuous user interaction.
  - **User Commands:**
    - `add`, `subtract`, `multiply`, `divide` - Perform corresponding operations.
    - `history` - Display a list of past calculations.
    - `exit` - Exit the application.
    - `help` - Display available commands.
  - **Error Handling:** Gracefully handle invalid inputs and exceptional scenarios (e.g., division by zero).
  - **Data Management with pandas:**
    - **History Management:** Store calculation history using `pandas` DataFrames.
    - **Persistence:** Automatically save and load history from CSV files.
  - **Logging:** Implement logging to record calculation events and errors.
  - **Configuration Management:** Use environment variables to manage settings like history size and precision using the `dotenv` library.

- **Testing:**
  - Write unit tests using `pytest` to cover all functionalities.
  - Achieve at least **90% test coverage**.

- **Documentation:**
  - Provide a `README.md` with setup and usage instructions.
  - Include docstrings and inline comments for clarity.

### **2. Enhanced Calculator (Grade A)**

**Objective:** Develop a sophisticated calculator that incorporates advanced design patterns, data management, and extensive testing to provide a robust and scalable application.

**Requirements:**

- **Supported Operations:**
  - Addition
  - Subtraction
  - Multiplication
  - Division
  - Power (Exponentiation)
  - Root

- **Features:**
  - **REPL Interface:** Implement a robust Read-Eval-Print Loop for enhanced user interaction.
  - **Design Patterns Integration:**
    - **Factory Pattern:** Dynamically create operation instances based on user input.
    - **Observer Pattern:** Notify observers (e.g., logging, auto-saving) upon new calculations.
    - **Memento Pattern:** Implement undo and redo functionalities by capturing the calculator's state.
    - **Strategy Pattern:** Allow interchangeable operation execution strategies.
    - **Facade Pattern:** Provide a simplified interface to complex subsystems within the calculator.
  - **Data Management with pandas:**
    - **History Management:** Store calculation history using `pandas` DataFrames.
    - **Persistence:** Automatically save and load history from CSV files.
  - **Logging:** Implement logging to record calculation events and errors.
  - **Configuration Management:** Utilize environment variables and the `dotenv` library for flexible configuration.
  - **User Commands:**
    - `add`, `subtract`, `multiply`, `divide`, `power`, `root` - Perform corresponding operations.
    - `history` - Display a list of past calculations.
    - `undo`, `redo` - Undo or redo the last operation.
    - `save`, `load` - Manually save or load calculation history.
    - `clear` - Clear the calculation history.
    - `exit` - Exit the application.
    - `help` - Display available commands.
  - **Error Handling:** Comprehensive error handling covering input validation, operational errors, and configuration issues.

- **Testing:**
  - Write comprehensive unit and parameterized tests using `pytest` to cover all functionalities and edge cases.
  - Achieve **100% test coverage**, ensuring all code paths are tested.

- **Continuous Integration (CI):**
  - Configure GitHub Actions to automate testing and enforce **100% test coverage**.
  - Set up the CI pipeline to fail builds if coverage falls below **100%**, prompting immediate attention.

- **Documentation:**
  - Provide a detailed `README.md` with setup, usage, and testing instructions.
  - Include comprehensive docstrings and inline comments for maintainability.
  - Create supplementary documentation for design patterns and architectural decisions.

## **Project Structure**

Organize your project with a clear and modular directory layout to enhance readability and maintainability. Below is a recommended structure:

```
calculator_project/
├── app/
│   ├── __init__.py
│   ├── calculator_repl.py
│   ├── calculation.py
│   ├── calculator_config.py
│   ├── calculator_memento.py
│   ├── exceptions.py
│   ├── history.py
│   ├── input_validators.py
│   └── operations.py
├── tests/
│   ├── test_calculations.py
│   ├── test_calculator_repl.py
│   ├── test_calculator_config.py
│   ├── test_calculator_memento.py
│   ├── test_exceptions.py
│   ├── test_history.py
│   ├── test_input_validators.py
│   └── test_operations.py
├── .github/
│   └── workflows/
│       └── python-app.yml
├── .env
├── .gitignore
├── README.md
├── requirements.txt
└── setup.py
```

## **Setup Instructions**

### **1. Repository Setup**

1. **Initialize Git Repository:**
   - Create a new Git repository locally and push it to GitHub.
   - Ensure the repository is public or accessible to your instructors.

2. **Project Directory:**
   - Organize your project files following the structure outlined above.

3. **Virtual Environment:**
   - Create and activate a Python virtual environment to manage dependencies.
     ```bash
     python3 -m venv venv
     source venv/bin/activate  # On Windows: venv\Scripts\activate
     ```

4. **Install Dependencies:**
   - Create a `requirements.txt` file with the necessary packages.
     ```plaintext
     pandas
     pytest
     pytest-cov
     python-dotenv
     ```
   - Install dependencies using pip.
     ```bash
     pip install -r requirements.txt
     ```

5. **Environment Variables:**
   - Create a `.env` file in the root directory to manage configuration settings.
     ```dotenv
     CALCULATOR_BASE_DIR=./app
     CALCULATOR_MAX_HISTORY_SIZE=1000
     CALCULATOR_AUTO_SAVE=true
     CALCULATOR_PRECISION=10
     CALCULATOR_MAX_INPUT_VALUE=1e999
     CALCULATOR_DEFAULT_ENCODING=utf-8
     CALCULATOR_LOG_DIR=./logs
     CALCULATOR_HISTORY_DIR=./history
     CALCULATOR_HISTORY_FILE=./history/calculator_history.csv
     CALCULATOR_LOG_FILE=./logs/calculator.log
     ```

### **2. Application Development**

**Basic Calculator (Grade B):**

- **Implement Basic Functionalities:**
  - Develop basic arithmetic operations (`add`, `subtract`, `multiply`, `divide`).
  - Ensure the REPL interface is functional and user-friendly.
  - Integrate `pandas` for managing calculation history.
  - Implement logging to track operations and errors.
  
- **Error Handling:**
  - Handle invalid inputs gracefully, such as non-numeric entries and division by zero.

- **Testing:**
  - Write unit tests covering all operations and edge cases.
  - Ensure at least **90% test coverage** using `pytest` and `pytest-cov`.

**Enhanced Calculator (Grade A):**

- **Implement Advanced Functionalities:**
  - Develop additional arithmetic operations (`power`, `root`).
  - Integrate advanced design patterns:
    - **Factory Pattern:** Dynamically create operation instances based on user input.
    - **Observer Pattern:** Notify observers (e.g., logging, auto-saving) upon new calculations.
    - **Memento Pattern:** Implement undo and redo functionalities by capturing the calculator's state.
    - **Strategy Pattern:** Allow interchangeable operation execution strategies.
    - **Facade Pattern:** Provide a simplified interface to complex subsystems within the calculator.
  - Utilize `pandas` for enhanced history management and data persistence.
  - Implement comprehensive logging to track detailed operation events and errors.

- **Error Handling:**
  - Implement comprehensive error handling covering input validation, operational errors, and configuration issues.

- **Testing:**
  - Write comprehensive unit and parameterized tests covering all functionalities and edge cases.
  - Achieve **100% test coverage** using `pytest` and `pytest-cov`.

- **Continuous Integration (CI):**
  - Configure GitHub Actions to automate testing and enforce **100% test coverage**.
  - Ensure the CI pipeline fails builds if coverage falls below **100%**, prompting immediate attention.

### **3. Testing**

- **Unit Tests:**
  - Write tests for each module and functionality in the `tests/` directory using `pytest`.
  - Ensure tests cover both typical use cases and edge cases.

- **Test Coverage:**
  - Use `pytest-cov` to measure test coverage.
  - **Basic Calculator (Grade B):** Aim for at least **90% coverage**.
  - **Enhanced Calculator (Grade A):** Achieve **100% coverage**.

- **Coverage Exceptions:**
  - Use `# pragma: no cover` comments for lines that are not critical to test coverage, such as logging statements or exception handlers that are difficult to trigger.
  
  ```python
  def some_method():
      try:
          # some code
          pass
      except SomeException:
          handle_exception()  # pragma: no cover
  ```

### **4. Continuous Integration (CI) with GitHub Actions**

- **Setup GitHub Actions Workflow:**
  - Create a workflow file at `.github/workflows/python-app.yml` with the following configuration:
  
    ```yaml
    name: Python application

    on:
      push:
        branches: [ main ]
      pull_request:
        branches: [ main ]

    jobs:
      build:

        runs-on: ubuntu-latest

        steps:
        - uses: actions/checkout@v2
        - name: Set up Python 3.x
          uses: actions/setup-python@v2
          with:
            python-version: '3.x'
        - name: Install dependencies
          run: |
            python -m pip install --upgrade pip
            pip install -r requirements.txt
        - name: Run tests with coverage
          run: |
            pytest --cov=app tests/
        - name: Check coverage
          run: |
            coverage report --fail-under=90  # Set to 100 for Enhanced Calculator
    ```
  
  - **For Basic Calculator (Grade B):**
    - Set `--fail-under=90` to ensure at least **90% test coverage**.
  
  - **For Enhanced Calculator (Grade A):**
    - Modify `--fail-under=90` to `--fail-under=100` to enforce **100% test coverage**.

- **Enforce Coverage Standards:**
  - Ensure that the CI pipeline fails if coverage thresholds are not met, prompting students to write additional tests.

### **5. Documentation**

- **README.md:**
  - Provide comprehensive setup and usage instructions.
  - Include examples of how to run the application and execute tests.
  - Explain the project structure and design patterns used.

- **Code Documentation:**
  - Use docstrings and inline comments to explain the purpose and functionality of classes, methods, and complex code blocks.
  - Ensure that all modules are well-documented to facilitate understanding and maintainability.

## **Academic Integrity**

**Academic Integrity** is a fundamental aspect of your educational journey. Upholding these principles ensures fairness, trust, and respect within the academic community. **Cheating, plagiarism, and any form of academic dishonesty are strictly prohibited** and will result in severe consequences.

### **Key Principles:**

- **Original Work:** All code submitted must be your own. Collaborating with peers is allowed only as specified by the course guidelines.
- **Proper Attribution:** If you reference or utilize external resources, libraries, or code snippets, they must be properly cited.
- **No Unauthorized Assistance:** Seeking help from unauthorized sources, including online platforms beyond course materials, is prohibited.

### **Git Commit Requirements:**

To maintain academic integrity and demonstrate your development process, adhere to the following Git commit standards:

1. **Frequent Commits:**
   - **Reasonable Frequency:** Commit your code regularly (e.g., after implementing a new feature, fixing a bug, or making significant changes). This demonstrates incremental progress and facilitates tracking your development process.
   - **Avoid Large Commits:** Refrain from making excessively large commits that encapsulate multiple unrelated changes. Instead, break them down into smaller, manageable commits.

2. **Descriptive Commit Messages:**
   - **Clarity:** Each commit message should clearly describe the changes made. This helps in understanding the evolution of your project.
   - **Consistency:** Follow a consistent format for commit messages, such as the [Conventional Commits](https://www.conventionalcommits.org/) standard.
   - **Examples:**
     - `feat: Implement addition operation`
     - `fix: Handle division by zero error`
     - `docs: Update README with setup instructions`
     - `test: Add unit tests for subtraction operation`

3. **Matching Tests with Code:**
   - **Synchronized Development:** Whenever you add or modify a feature, ensure that corresponding tests are also written or updated in the same commit.
   - **Commit Pairing:** Structure your commits to pair implementation changes with their tests. For example, first commit the feature, then commit the associated tests, or combine them into a single cohesive commit.
   - **Example:**
     - Commit 1: `feat: Add multiplication operation to calculator`
     - Commit 2: `test: Add unit tests for multiplication operation`

4. **Comprehensive History:**
   - **Granularity:** Ensure that each commit represents a single logical change. This makes it easier to review and revert changes if necessary.
   - **Avoid Merge Commits:** Where possible, use fast-forward merges to maintain a linear commit history. This simplifies the project history and enhances readability.

5. **Commit Integrity:**
   - **Complete Changes:** Each commit should include all necessary files and changes required for that specific update. Avoid partial commits that leave the project in an incomplete state.
   - **No Unrelated Files:** Ensure that only relevant files are included in each commit. Exclude temporary files, build artifacts, or other unrelated files using a `.gitignore` file.

### **Enforcement:**

- **GitHub Actions Integration:**
  - **Automated Checks:** Configure GitHub Actions to perform automated checks on commit messages and enforce commit standards.
  - **Hooks and Scripts:** Utilize Git hooks or scripts to validate commit messages and ensure that tests are included alongside code changes.
  
- **Instructor Review:**
  - **Commit History Evaluation:** Instructors will review your commit history to assess adherence to the commit standards and academic integrity policies.
  - **Consistency and Transparency:** A well-structured commit history reflects a transparent and disciplined development process.

### **Consequences of Academic Dishonesty:**

Violations of academic integrity policies will result in disciplinary actions, which may include:

- **Grade Penalties:** Reduction or forfeiture of project grades.
- **Course Failure:** Failure of the project or the entire course, depending on the severity of the violation.
- **Further Disciplinary Actions:** Additional consequences as per institutional policies.

**Always strive to produce your own work, understand the material, and seek help through authorized channels such as instructors, teaching assistants, and official course forums.**

## **Submission Instructions**

1. **GitHub Repository:**
   - Ensure your code is pushed to GitHub with a clear and descriptive commit history.
   - The repository should follow the prescribed directory structure.
   - Include a detailed `README.md` with all necessary information.

2. **Testing:**
   - Ensure that all tests pass locally before submission.
   - Verify that the GitHub Actions workflow runs successfully and enforces the coverage requirements.

3. **Final Submission:**
   - Submit the link to your GitHub repository through the designated platform (e.g., course management system).

## **Grading Criteria**

### **Basic Calculator (Grade B):**

- **Functionality (30%):** Correct implementation of basic arithmetic operations and user commands.
- **Data Management with pandas (15%):** Effective use of `pandas` for storing and retrieving calculation history.
- **Logging (15%):** Proper implementation of logging to track operations and errors.
- **Error Handling (20%):** Robust handling of invalid inputs and exceptional scenarios.
- **Testing (15%):** Comprehensive unit tests achieving at least **90% test coverage**.
- **Documentation (5%):** Clear and concise documentation with a well-structured `README.md`.

### **Enhanced Calculator (Grade A):**

- **Functionality (25%):** Complete implementation of all specified operations and advanced user commands.
- **Design Patterns (25%):** Effective integration of Factory, Observer, Memento, Strategy, and Facade patterns.
- **Data Management with pandas (15%):** Efficient use of `pandas` for history management and data persistence.
- **Logging (10%):** Comprehensive logging to record detailed operation events and errors.
- **Error Handling (10%):** Comprehensive and sophisticated error management covering all possible scenarios.
- **Testing (10%):** Exhaustive unit and parameterized tests achieving **100% test coverage**.
- **Continuous Integration (5%):** Proper setup and functioning of GitHub Actions to enforce coverage standards.
- **Documentation (5%):** Detailed and thorough documentation, including explanations of design patterns and architectural decisions.

## **Suggested Project Workflow**

1. **Planning:**
   - Outline the features and functionalities you intend to implement.
   - Design the architecture, especially if opting for the Enhanced Calculator with multiple design patterns.

2. **Development:**
   - Start by setting up the project structure and configuring environment variables.
   - Implement the core functionalities first (Basic Calculator operations), then progressively add more features.
   - Integrate `pandas` and `logging` early to ensure consistent data management and event tracking.

3. **Testing:**
   - Write unit tests alongside your development to ensure each component works as intended.
   - Use `pytest` and `pytest-cov` to monitor test coverage continuously.
   - Address any coverage gaps before proceeding.

4. **Continuous Integration:**
   - Set up GitHub Actions to automate testing on every push or pull request.
   - Ensure that the CI pipeline enforces the required coverage thresholds.

5. **Documentation:**
   - Maintain comprehensive documentation throughout the development process.
   - Update the `README.md` with any new features or changes.

6. **Final Review:**
   - Conduct a thorough review of your codebase to ensure all requirements are met.
   - Validate that all tests pass and coverage thresholds are achieved.
   - Ensure that the GitHub Actions workflow is functioning correctly.

## **Conclusion**

This mid-term project is an opportunity to showcase your proficiency in Python programming, software design, data management, and testing. Whether you opt for the Basic or Enhanced Calculator, ensure that your application is well-designed, thoroughly tested, and meticulously documented. Embrace the challenge to apply the concepts learned and produce a high-quality software solution.

If you have any questions or require further assistance, feel free to reach out through the course forums or office hours. Good luck, and happy coding!