# AutomationProject

Repository: https://github.com/hazem-elgenidy/AutomationProject.git  
Branch: main

## Summary
Selenium-based Java automation project using Maven. Contains a simple WebDriver factory (`src/main/java/DriverFactory.java`) that provides a singleton `ChromeDriver` and a `quitDriver` helper.

## Tech stack
- Java (11+)
- Maven
- Selenium WebDriver
- Chrome browser / ChromeDriver
- IntelliJ IDEA (development)

## Prerequisites
- Java JDK 11 or later installed
- Maven installed
- Google Chrome installed (version must match ChromeDriver)
- ChromeDriver binary available in `PATH` or provide its path via system property

## Setup & run
1. Clone the repository:
   - `git clone https://github.com/hazem-elgenidy/AutomationProject.git`
   - `cd AutomationProject`

2. Option A — add `chromedriver` to system `PATH` and run tests:
   - `mvn clean test`

   Option B — pass ChromeDriver path explicitly (Windows example):
   - `mvn -Dwebdriver.chrome.driver="C:\path\to\chromedriver.exe" clean test`

3. Run a specific test class:
   - `mvn -Dtest=MyTestClass test`

## Usage (example)
Example test code using the driver factory:

    WebDriver driver = DriverFactory.getDriver();
    driver.get("https://example.com");
    // ... test steps ...
    DriverFactory.quitDriver();

## DriverFactory behavior
- Lazily initializes a single `ChromeDriver` instance on first call to `getDriver()`.
- Calls `driver.manage().window().maximize()` after creation.
- `quitDriver()` quits the browser and sets the stored driver reference to `null`.

