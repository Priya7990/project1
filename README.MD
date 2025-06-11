# 🧪 Ecommerce Automation Framework with Selenium Design Framework (Java, TestNG, Maven, Jenkins (CI/CD))Add commentMore actions

## Overview

The Ecommerce Automation Framework is a Selenium-based test automation setup designed to test an ecommerce application. It includes:

- End-to-end tests
- API tests
- Validation tests
- Reusable utilities

The framework is **modular**, **scalable**, and **easy to use** for both beginners and experienced testers.

This project is a Java-based Selenium test automation framework following the **Page Object Model (POM)** design pattern. The framework supports both **UI end-to-end testing**, and is organized for **clarity**, **scalability**, and **maintainability**.

---

## 📁 Project Structure
```text
/project-root
│
├── src/
│   └── main/
│       └── java/
│           ├── AbstractComponents/
│           │   └── AbstractComponents.java              # Base class to manage and return page objects
│           │
│           ├── pageObjects/                             # Page Object Model (POM) classes
│           │   ├── CartPage.java                         # Logic for cart page
│           │   ├── ConfirmationPage.java                 # Confirmation page locators/actions
│           │   ├── LandingPage.java                      # Login page elements
│           │   ├── OrderPage.java                        # Checkout/order review logic
│           │   ├── PaymentPage.java                      # Payment page handling
│           │   └── ProductCataloguePage.java             # Product catalog interaction
│           │
│           └── resources/                               # Utility & config files
│               ├── ExtentReporterNG.java                # ExtentReports configuration
│               └── GlobalData.properties                # Global settings (e.g., browser, URL)
│
│   └── test/
│       └── java/
│           ├── data/
│           │   ├── DataReader.java                      # Reads data from JSON to HashMap
│           │   └── PurchaseOrder.json                   # JSON test data for purchase flow
|
|           ├── cucumber/
│           │   ├── TestNGTestRunner.java                # TestRunner for cucumber feature files
│           │   └── ErrorValidation.feature              # feature file for error validation
│           │   └── SubmitOrder.feature                  # feature file for submit order
│
│           ├── stepDefinitions/
│           │   ├── ErrorValidationStepDefinition.java    # Step Definitions for Error Validation
│           │   ├── StepDefinitionImplementation.java     # Step Definition for Submit Order
|
│           ├── testComponents/
│           │   ├── BaseTest.java                        # WebDriver setup/teardown
│           │   ├── Listeners.java                       # ExtentReport TestNG listener
│           │   └── Retry.java                           # Retry logic for flaky tests
│
│           └── tests/                                   # Actual test classes
│               ├── ErrorValidationTest.java             # Tests for invalid scenarios
│               ├── StandaloneTest.java                  # Example standalone test
│               └── SubmitOrderTest.java                 # End-to-end purchase test
│
├── testSuites/                                          # TestNG suite XMLs
│   ├── ErrorValidationTests.xml                         # Runs validation tests
│   ├── Purchase.xml                                     # Runs order placement tests
│   └── testng.xml                                       # Master suite file
│
└── pom.xml                                              # Maven project config (dependencies, plugins)

## ✅ Key Components

### 🔹 `pageObjects/`
- Encapsulates all web page interactions using the **Page Object Model (POM)**.
- Each class maps to a web page or screen and provides **reusable methods** for UI interaction.

### 🔹 `AbstractComponents/`
- Contains abstract base classes like `AbstractComponents.java`.
- Provides shared utilities like **wait handlers**, **click actions**, and other reusable functions.

### 🔹 `testComponents/`
- `BaseTest.java`: Sets up the **WebDriver** and common test configuration.
- `Listeners.java`: Hooks into the **TestNG** lifecycle for custom logging/reporting.
- `Retry.java`: Enables **retry logic** to handle flaky tests.

### 🔹 `tests/`
- Contains actual **test cases**, organized by features (e.g., validation, checkout).
- Follows **modular** and **data-driven** design.

### 🔹 `resources/`
- Configuration files like `GlobalData.properties` for environment-specific variables.
- `ExtentReporterNG.java` for customizing test reports.

### 🔹 `data/`
- Stores test input files such as `PurchaseOrder.json`.
- Includes data utilities like `DataReader.java`.

### 🔹 `testSuites/`
- Holds specific and master **TestNG XML suite files** to run grouped test sets.

---

## 🛠 Tech Stack

- Java 11+
- Selenium WebDriver
- TestNG
- Maven
- Extent Reports
- Jackson / Gson (for JSON parsing)
- Jenkins (for CI/CD integration)
- Cucumber (basic BDD: feature files, step definitions, test runners)

---

## 🚀 Getting Started

### 1. Install Dependencies
```bash
mvn clean install

### **2. Run All tests**
mvn test

### **3. Run specific suite**
mvn test -P ProfileNameFromPom (eg: mvn test -P Purchase)

### **4. To run cucumber tests**
mvn test -P CucumberTests
