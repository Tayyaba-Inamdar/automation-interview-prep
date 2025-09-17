### **Q. In Selenium, what’s the difference between absolute XPath and relative XPath? Give example.**

✅ **Answer:**

* **Absolute XPath**: Starts from the root (`/html/body/...`). Very long, breaks if UI changes.
  ```xpath
  /html/body/div[1]/div[2]/form/input[1]
  ```
* **Relative XPath**: Starts with `//`, shorter, more flexible.
  ```xpath
  //input[@id='username']
  ```
---

### **Q. What is the difference between `//` and `/` in XPath?**

✅ **Answer:**

* `/` → Selects from the **root node only**.
* `//` → Can start **from anywhere in the DOM**, skips hierarchy.

---

### **Q. Types of waits in Selenium? Syntax + When to use which?**

✅ **Answer:**

1. **Implicit Wait** – Global wait, applies to all elements.

   ```java
   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
   ```
2. **Explicit Wait** – Wait for specific condition.

   ```java
   WebDriverWait wait = new WebDriverWait(driver, 10);
   wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("username")));
   ```
3. **Fluent Wait** – Like explicit, but allows polling frequency + ignore exceptions.

   ```java
   Wait<WebDriver> wait = new FluentWait<>(driver)
       .withTimeout(Duration.ofSeconds(10))
       .pollingEvery(Duration.ofSeconds(2))
       .ignoring(NoSuchElementException.class);
   ```

---

### **Q. Tell me Selenium navigation commands.**

✅ **Answer:**

```java
driver.navigate().to("https://example.com");
driver.navigate().back();
driver.navigate().forward();
driver.navigate().refresh();
```

---

### **Q. In Rest Assured, what is the difference between BaseURI and BasePath? Show small code.**

✅ **Answer:**

* **BaseURI** = domain (common root URL).
* **BasePath** = the initial URL segment that comes after the base URI .

```java
RestAssured.baseURI = "https://reqres.in";
RestAssured.basePath = "/api";

given().get("/users?page=2").then().statusCode(200);
```

---
---

### **Q. What is the difference between Path Parameter and Query Parameter in APIs?**

✅ **Answer:**

* **Path Parameter**: Part of the URL → identifies a specific resource.
  Example: `/users/{id}` → `/users/101`

  ```java
  given().pathParam("id", 101).get("/users/{id}");
  ```
* **Query Parameter**: Added after `?` in the URL → used for filtering/searching.
  Example: `/users?page=2`

  ```java
  given().queryParam("page", 2).get("/users");
  ```

---
### **Q. Write code to verify response status code in Rest Assured.**

✅ **Answer:**

```java
given()
    .when().get("/users/2")
    .then().statusCode(200);
```

---
### **Q. Write a Rest Assured script to fetch a user profile and validate username**

✅ **Answer:**

```java
Response response = given()
    .when().get("https://reqres.in/api/users/2");

response.then().statusCode(200);

// Validate username
String username = response.jsonPath().getString("data.first_name");
Assert.assertEquals(username, "Janet");
```
---
### **Q. Validate response / status code in Rest Assured**

✅ **Answer:**

```java
given()
    .when().get("/users/2")
    .then()
    .statusCode(200)
    .body("data.id", equalTo(2));
```
---

### **Q. How do you fetch and validate cookies in Rest Assured?**

✅ **Answer:**

```java
Response response = given().get("/users/2");
String cookie = response.getCookie("session_id");
Assert.assertNotNull(cookie);
```
---

### **Q. Show me how to upload a file in Rest Assured.**

✅ **Answer:**

```java
File ufile = new File("src/test/resources/testfile.txt");

given()
    .multiPart("file", ufile)
    .when()
    .post("/upload")
    .then()
    .statusCode(200);
```

---

### **Q. Response codes (201, 204, 300)**

✅ **Answer:**

* **201 Created** → Resource successfully created (e.g., POST new user).
* **204 No Content** → Request succeeded but no content in response (e.g., DELETE success).
* **300 Multiple Choices** → Multiple possible responses (rare in modern REST APIs, mostly redirection).

---

### **Q. API Security Testing**

✅ **Answer:**
Focus areas:

* **Authentication & Authorization** → check with/without tokens, expired tokens.
* **Input Validation** → test for SQL injection, XSS, invalid payloads.
* **Rate Limiting** → send multiple requests quickly, check throttling.
* **HTTPS Only** → verify secure transport.

Example check with missing token:

```java
given()
    .when().get("/secure/profile")
    .then().statusCode(401);
```
---
### **Q. Mock API**

✅ **Answer:**

* A **Mock API** simulates real API responses without hitting the actual backend.
* Useful when the backend isn’t ready but QA/dev need to test.
* Tools: Postman Mock Server, WireMock, JSON Server.
---

### **Q. Negative Testing in API**

✅ **Answer:**
Examples:

* Missing required fields in request body.
* Invalid data types (e.g., string instead of integer).
* Unauthorized access (wrong token).
* Invalid endpoint (404).

```java
given()
    .body("{ \"name\": 12345 }") // invalid type
    .when().post("/users")
    .then().statusCode(400);
```

---



