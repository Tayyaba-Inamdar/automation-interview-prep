## ✅ Java Programming

### ➤ Core Java & OOPs

* What is method Overloading and method Overriding?
* Difference between abstraction and interface?
* What is this and super keyword? Can we use both in the same method and constructor? 
  <details>
  <summary>What is type casting and its types?</summary>
    JavascriptExecutor js = (JavascriptExecutor)driver; // Cast WebDriver → JS Executor
    
    String title = (String)js.executeScript("return document.title"); // Cast Object → String
  </details>

* What are Constructors in Java?
* What does super() keyword do in Java?
* Can you explain the difference between throw and throws in Java?
* What is the purpose of the static keyword in Java?
* What collection topics have you used in your framework?
* Difference between ArrayList and LinkedList?


### ➤ Coding Challenges
* WJP to count the occurrence of each character in a string
* WJP to convert LinkedList to HashSet
* WJP for given strings are anagram or not: str1="tomato", str2="matoto"
* WJP to remove duplicates from given string| str1="automation" → "automin" | Input="characters" → Output="chartes"
* String problem: Input -> "aaAAbbCCddd" → Output: "a2A2C2d3"
* Write function to find the sum of distinct elements in an array
* Print each letter twice: Input="hello" → Output="hheelllloo"
* Count odd and even numbers from array
* Swap two strings without third variable

---

## ✅ Selenium

### ➤ Selenium Basics

<details>
  <summary>Explain Selenium3 vs Selenium4 architecture</summary>
Test Script
   ↓
WebDriver API
   ↓  (JSON Wire Protocol)
Browser Driver
   ↓  (translates to W3C)
Browser


Test Script
   ↓
WebDriver API
   ↓  (W3C Protocol — native)
Browser Driver
   ↓
Browser

Selenium 3: WebDriver speaks one language (JSON Wire), browser drivers speak another (W3C), so translation is needed.
Selenium 4: Everyone speaks the same language (W3C protocol) — more reliable communication.
</details>

* Difference between RemoteDriver and WebDriver
🔹 WebDriver (Interface)
It's a top-level interface in Selenium.
Provides the main methods like .get(), .click(), .findElement(), etc.
Implemented by many browser-specific classes:
WebDriver driver = new ChromeDriver();  // local testing
🔹 RemoteWebDriver (Class)
A concrete class that implements the WebDriver interface.
Used when running tests remotely, e.g.:
On a Selenium Grid
On cloud services like BrowserStack, Sauce Labs
Communicates via the WebDriver protocol (HTTP).
WebDriver driver = new RemoteWebDriver(new URL("http://localhost:4444/wd/hub"), options);

* What is the Action class in Selenium? Mention a few methods
* What is JavaScriptExecutor, when to use it? Write syntax
* Difference between get() and navigate.to()
* Syntax to take screenshot & type casting used
* Syntax for performing "Control + A"
* Difference between build() and perform()
* How to perform right-click operation?
* How to scroll to a particular section? Write syntax
* Difference between verification and validation
* How to handle dynamic elements in Selenium
* Topmost interface in Selenium

### ➤ Frameworks & Execution

* Explain the Selenium framework you've used
* How to execute failed test cases without manual intervention (Retry mechanism)?
* How to execute all failed test cases at once after initial execution?
* How to execute only 10 out of 100 test cases in Cucumber?
* How to perform cross-browser testing?

---

## ✅ TestNG

* How to perform parallel testing?
* TestNG annotations used and explanation of each

---

## ✅ Cucumber

* What is BDD? How does it work?
* Why use Background keyword?
* Difference between Scenario and Scenario Outline?
* Why use the Examples keyword?

---

## ✅ API Testing / Rest Assured

* Write a Rest Assured script to fetch a user profile and validate username
* What is the difference between path parameter and query parameter in APIs?

---

## ✅ SQL

* Given Tables: Artist(id, name), Songs(song\_id, song\_name, artist\_id) → Query to get each artist’s song count
* Query to get the second highest salary
* What is a self join? Syntax for manager-employee relation
* What are aggregate functions? Name a few

---

## ✅ Git

* Difference between git pull and git patch

---

## ✅ Agile & Testing Strategy

* What does "Velocity" refer to in Agile Testing?
* What is the strategy to start failure analysis from Day 1?
* How to calculate ROI for automation?
* How to identify test cases that can be automated?
* How to determine test execution time with dependencies like mocks and test data?
* What are the key benefits of Automation Testing over Manual Testing?
* What are the advantages and disadvantages of automation frameworks?
* What factors to consider when selecting an automation tool?

---

## ✅ QA Roles & Management

* Introduce Yourself
* Explain your roles and responsibilities in the project
* How to assign work to Seniors vs. Juniors (1–2 yrs)?
* As a QA Lead, what is your checklist for code review?
* Describe a critical defect you found during testing
* How to handle rejected bug reports?
* Define Severity and Priority
* Example of High Priority but Low Severity bug

---

## ✅ Miscellaneous

* Write a script to select a specific city from a dropdown (100+ options)
* Java statement meaning: WebDriver driver = new FirefoxDriver();
