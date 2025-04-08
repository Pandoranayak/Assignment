# Playwright Coding Assignment

This assignment demonstrates the use of Playwright for browser automation, Python for scripting, and Behave for implementing Behavior-Driven Development (BDD).

## Overview

This assignment [briefly describe the purpose of your assignment - e.g., automates user interactions on a specific website, tests a particular web application feature].  It uses Playwright to control web browsers, Python to drive the automation, and Behave to structure the tests in a clear, readable format.

## Technologies Used

* **Playwright:** A library for automating web browsers.  This project uses the Playwright Python bindings.
* **Python:** The scripting language used to write the automation code.
* **Behave:** A Behavior-Driven Development (BDD) framework.  Behave uses Gherkin syntax to define test scenarios.

## Setup Instructions

Follow these steps to set up the project:

1.  **Prerequisites:**

    * **Python:** Ensure Python 3.7 or later is installed.  Download from [https://www.python.org/downloads/](https://www.python.org/downloads/).
    * **pip:** Python's package installer (usually included with Python).

2.  **Clone the Repository:**

    ```bash
    git clone [your-repository-url]
    cd [your-repository-name]
    ```

3.  **Activate the virtual environment in the project**
    As there is a virtual environment inside the project path, there is no need to install dependencies

    * Open a terminal in the project root and enter the following command:
    ```bash
    source bin/activate
    ```



## Running the Tests

To run the Behave tests:

* Run the below command in the project root directory
  
```bash
behave
This will execute all feature files in the features/ directory.

Project Structure. Here's my project structure:
├── features/
│   ├── menu_item_validation.feature     # Feature files in Gherkin
│   └── partial_purchase_flow.feature
├── steps/
│   ├── menu_item_validation_step.py           # Python code to implement Gherkin steps
│   └── partial_purchase_flow_steps.py
├── requirements.txt         # Python dependencies
├── environment.py        # Browser context and logger functionality
└── README.md                 # This file


features/: Contains feature files written in Gherkin (e.g., my_feature.feature).  These describe the behavior of the system.steps/: Contains Python files (e.g., steps.py) that define the actions to take for each Gherkin step.pages/

 Example (my_feature.feature)Feature: User Login
  Scenario: Successful login
    Given the user is on the login page
    When the user enters valid credentials
    And the user clicks the login button
    Then the user should be logged in

