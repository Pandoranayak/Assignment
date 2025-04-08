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

    ```source bin/activate
    ```

    * Create a `requirements.txt` file in the project root.  It should contain:

        ```text
        playwright
        behave
        ```
        (and any other Python packages you use).

5.  **Install Playwright Browsers:**

    ```bash
    playwright install
    ```
    * This command downloads the browsers (Chromium, Firefox, WebKit) that Playwright will automate.

## Running the Tests

To run the Behave tests:

```bash
behave
This will execute all feature files in the features/ directory.To run a specific feature or scenario:behave features/my_feature.feature
behave features/my_feature.feature:10 # Run scenario on line 10
Project StructureHere's a typical project structure:[your-repository-name]/
├── features/
│   ├── my_feature.feature     # Feature files in Gherkin
│   └── ...
├── steps/
│   ├── steps.py             # Python code to implement Gherkin steps
│   └── ...
├── pages/                   # (Optional) Page Object Model
│   ├── base_page.py
│   ├── home_page.py
│   └── ...
├── requirements.txt         # Python dependencies
└── README.md                 # This file
features/: Contains feature files written in Gherkin (e.g., my_feature.feature).  These describe the behavior of the system.steps/: Contains Python files (e.g., steps.py) that define the actions to take for each Gherkin step.pages/ (Optional): If you're using the Page Object Model, this directory holds classes that represent web pages.requirements.txt: Lists the python dependencies.README.md: Provides an overview of the project.Gherkin Syntax Example (my_feature.feature)Feature: User Login
  Scenario: Successful login
    Given the user is on the login page
    When the user enters valid credentials
    And the user clicks the login button
    Then the user should be logged in
Python Step Definition Example (steps/steps.py)from behave import given, when, then
from playwright.sync_api import sync_playwright

# Example using a global browser and page.  For more robust
# projects, consider using Behave's "use_fixture" to manage
# the browser lifecycle.
browser = None
page = None

def before_all(context):
    global browser
    global page
    p = sync_playwright().start()
    browser = p.chromium.launch()
    page = browser.new_page()
    context.browser = browser # Make them available to steps
    context.page = page

def after_all(context):
    global browser
    global page
    if page:
       page.close()
    if browser:
        browser.close()

@given('the user is on the login page')
def step_impl(context):
    context.page.goto('[https://example.com/login](https://www.google.com/search?q=https://example.com/login)')  # Replace with your login URL

@when('the user enters valid credentials')
def step_impl(context):
    context.page.fill('input[name="username"]', 'myuser')  # Replace with your username field
    context.page.fill('input[name="password"]', 'mypassword')  # Replace with your password field

@when('the user clicks the login button')
def step_impl(context):
    context.page.click('button[type="submit"]')  # Replace with your login button selector

@then('the user should be logged in')
def step_impl(context):
    #  Replace with an appropriate check for successful login.
    #  For example, check for an element that only appears when logged in.
    expect(context.page.locator('div#dashboard').first).to_be_visible()
Further Information (Optional)Page Object Model: (If used) Explain how you've organized your page interactions using the Page Object Model.Test Data: Describe how test data is managed (e.g., hardcoded, external
