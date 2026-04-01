# sdet-parallel-ai-automation-framework
A scalable, thread-safe test automation framework built using Selenium, TestNG, and Java, designed for parallel execution and intelligent failure handling. Built with a focus on clean architecture, reliability, and real-world SDET practices. Designed to evolve with AI-assisted testing capabilities.
## Key Highlights

* ✅ Thread-safe WebDriver management using ThreadLocal
* ✅ Parallel execution support (methods / classes / tests)
* ✅ Config-driven execution (no hardcoding)
* ✅ Smart retry mechanism (failure-aware, not blind retries)
* ✅ Automatic screenshot capture on test failure
* ✅ Clean architecture (BaseTest + DriverFactory + Utilities)
* ✅ CI/CD ready (runtime overrides via system properties)

## Architecture Overview

base/
   BaseTest.java

driver/
   DriverManager.java
   BrowserFactory.java

utils/
   ConfigReader.java
   RetryAnalyzer.java
   ScreenshotUtil.java

listeners/
   TestListener.java

tests/
   TestClass1.java
   TestClass2.java


## Tech Stack

* Java
* Selenium WebDriver
* TestNG
* Maven

## Execution

### Run with default config:

mvn test

### Run with browser override:

mvn test -Dbrowser=chrome

## Parallel Execution

Configured via TestNG:

<suite name="Suite" parallel="methods" thread-count="3">

Supports:

* Parallel by methods
* Parallel by classes
* Parallel by tests

## Smart Retry Logic

Retries only for transient failures like:

* StaleElementReferenceException
* TimeoutException
* WebDriverException

Does NOT retry:

* Assertion failures
* Logical test failures

## Failure Handling (Inprogress)

* Automatic screenshot capture on failure
* Stored under `/screenshots`
* Helps debugging and failure analysis

## Design Principles (Done)

* Separation of concerns
* Thread safety first
* Minimal duplication
* Config over hardcoding
* Fail fast, retry smart
  
## Future Enhancements - (TO DO)

* AI-assisted test generation
* Self-healing locators
* Advanced reporting (Allure / Extent)
* API + UI unified framework
* Docker-based execution

## Author

Automation Engineer with 10+ years experience in building scalable test frameworks across Web, Mobile, and API layers.

