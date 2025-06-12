
# Selenium Design Framework 🧪

A robust and scalable automation framework using **Selenium**, **TestNG**, and **Maven**, designed for testing modern web applications efficiently with Page Object Model and reusable components.The Framework is a Selenium based test automation setup designed to test an ecommerce application. It supports both UI end-to-end testing, and is organized for clarity, scalability, and maintainability. 

---

## 🔧 Tech Stack

- Java 11+
- Selenium WebDriver
- TestNG
- Maven
- Page Object Model (POM)
- Extent Reports
- Data-Driven Framework
- Git & GitHub

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
│           ├── pageObjects/                             # Page Object Model (POM) classes
│           │   ├── CartPage.java
│           │   ├── ConfirmationPage.java
│           │   ├── LandingPage.java
│           │   ├── OrderPage.java
│           │   ├── PaymentPage.java
│           │   └── ProductCataloguePage.java
│           └── resources/
│               ├── ExtentReporterNG.java
│               └── GlobalData.properties
│
├── test/
│   └── java/
│       ├── data/
│       │   ├── DataReader.java
│       │   └── PurchaseOrder.json
│       ├── cucumber/
│       │   ├── TestNGTestRunner.java
│       │   ├── ErrorValidation.feature
│       │   └── SubmitOrder.feature
│       ├── stepDefinitions/
│       │   ├── ErrorValidationStepDefinition.java
│       │   └── StepDefinitionImplementation.java
│       ├── testComponents/
│       │   ├── BaseTest.java
│       │   ├── Listeners.java
│       │   └── Retry.java
│       └── tests/
│           ├── ErrorValidationTest.java
│           ├── StandaloneTest.java
│           └── SubmitOrderTest.java
│
├── testSuites/
│   ├── ErrorValidationTests.xml
│   ├── Purchase.xml
│   └── testng.xml
│
└── pom.xml
```

---

## 🚀 Getting Started

### 1. Install Dependencies

```bash
mvn clean install
```

---

### 2. Run All Tests

```bash
mvn test
```

---

### 3. Run Specific Suite

```bash
mvn test -P <ProfileNameFromPom>
```

**Example:**

```bash
mvn test -P Purchase
```

---

### 4. Run Cucumber Tests

```bash
mvn test -P CucumberTests
```


---

## ✅ Key Components 

🔹 **pageObjects/**  
Encapsulates all web page interactions using Page Object Model.  
Each class maps to a web page or screen and provides clear, reusable methods for UI interaction.

🔹 **AbstractComponents/**  
Contains abstract base classes like `AbstractComponents.java` which provide common utility methods such as wait handlers, click actions, etc., shared across all page objects.

🔹 **testComponents/**  
- `BaseTest.java` sets up the WebDriver and common configurations for tests.  
- `Listeners.java` hooks into the TestNG lifecycle for logging/reporting.  
- `Retry.java` provides retry mechanisms for test flakiness.

🔹 **tests/**  
Organized test cases by feature (e.g., validation, checkout, standalone tests).  
Designed to be modular and data-driven.

🔹 **resources/**  
Configuration files like `GlobalData.properties` for environment variables.  
Extent report customization class (`ExtentReporterNG.java`).

🔹 **data/**  
Stores test data like `PurchaseOrder.json` and utilities to read them (e.g., `DataReader.java`).

🔹 **testSuites/**  
Includes specific and master TestNG XML suites for running grouped tests.

