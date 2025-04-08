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
```
This will execute all feature files in the features/ directory.

```bash
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
```


## Features tested in this assignment

**1. Feature: Partial purchase flow for the website**

*Scenario 1: Open the website and validate the title and number of items in the page*
```text
- Open the URL
- Title is validated
- Number of items in the page is validated
- Mouse hover over the image
- Validates that the hover changes the image
```
*Scenario 2: Validate the items in the page after putting certain filters*
```text
- Open the URL
- User selects the sorting order
- User selects the price range (Drags the min and max value)
- User selects the category checkbox
- User selects the brand checkbox
- Validates that the items in the page after the filters are as per the conditions set by the filters
```
*Scenario 3: Validate the purchase flow when checking out a item*
```text
- Open the URL
- User clicks on a item
- User can navigate to the selected item page
- Validates that the item page information for the product matches the homepage
- User clicks on "+" button to increase the quantity
- Validates that the item quantity is increased by 1
- User clicks on "Add to cart button"
- Validates Item is added to cart and green notification is visible
- Validates the API call
- User clicks on "View cart" button
- Validate that the user is naviagted to the cart page
- User clicks on "Checkout" button
- Validates that the user is redirected to the sign in page
- User clicks on cart icon
- User clicks on the "x" button
- Validates that the item is removed from the cart
```

**2. Feature: Validating menu item categories**

*Scenario : Validating menu item category dropdown*
```text
- Open the URL
- User clicks on category
- Validating the items in the dropdown and the order of the items
- User clicks on one of the category
- Validated that the user is redirected to the selected category page and the url contains the category
- Validates the title of the landing page
```

   

