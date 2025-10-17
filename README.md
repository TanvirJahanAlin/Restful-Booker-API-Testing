
# 🧩 Restful Booker API Testing Project

### 📘 Overview

This project demonstrates **API Testing using Postman** for the [Restful Booker API](https://restful-booker.herokuapp.com/apidoc/index.html).  
Restful Booker is a simple **CRUD (Create, Read, Update, Delete)** API designed for practicing API testing techniques. It includes authentication and resets data every 10 minutes for testing consistency.

The testing process covers all key endpoints with different HTTP methods — **GET, POST, PUT, PATCH, and DELETE** — and validates both **positive and negative scenarios**.

----------

### 🧰 Tools & Technologies

| Tool | Purpose |
|--|--|
| **Postman** | For creating, managing, and executing API requests |
| **Excel Sheet** | For maintaining detailed test cases, preconditions, steps, expected results etc. |
| **Restful Booker API** | The testing target API (publicly available) |

----------

### 📂 Project Structure

| File Name | Description  |
|--|--|
| `restful-booker.postman_collection.json` | The complete Postman collection with all requests and tests |
| `Test cases for API testing Restful Booker.xlsx` | Excel file containing detailed test cases for each endpoint |

---------

### 🧠 API Endpoints Tested

|No|Endpoint|Method|Purpose|
|--|--|--|--|
|1|`/ping`|**GET**|Health check to verify API availability|
|2|`/auth`|**POST**|Generate authentication token for secure requests|
|3|`/booking`|**GET**|Retrieve all booking IDs|
|4|`/booking/:id`|**GET**|Retrieve specific booking details by ID|
|5|`/booking`|**POST**|Create a new booking|
|6|`/booking/:id`|**PUT**|Update an existing booking (requires token)|
|7|`/booking/:id`|**PATCH**|Partially update an existing booking (requires token)|
|8|`/booking/:id`|**DELETE**|Delete a booking (requires token)|

---------

### ⚙️ How to Run the Project

#### **Step 1: Import Collection**

1.  Open **Postman**
    
2.  Click **Import → Upload Files**
    
3.  Select the file `restful-booker.postman_collection.json`
    

#### **Step 2: Set Environment Variable**

-   Create a variable `baseURL` with value:

	> `https://restful-booker.herokuapp.com`

#### **Step 3: Run Tests**

-   Use **Collection Runner** in Postman to execute all requests sequentially.
    
-   Verify the response status, body, and headers.
    

#### **Step 4: Precondition Example (Ping Test)**
|Step| Action |
|--|--|
| 1 | Pre-load Postman with the base URL and collection |
| 2 | Send GET request to `/ping` |
| ✅ Expected Result | Status code **201 Created** or **201 OK**, and response message `Created` or `HealthCheck Passed` depending on API state. |

-----------
### 📊 Test Coverage Summary

| Test ID | Test Scenario | Expected Result | Status |
|--|--|--|--|
| TC_01 | Health check of API | Returns 201 Created | ✅ Passed |
| TC_02 | Create token with valid credentials | Token generated successfully | ✅ Passed |
| TC_03 | Get booking by valid ID | Returns booking details | ✅ Passed |
| TC_04 | Update booking with valid token | Booking updated successfully | ✅ Passed |
| TC_05 | Delete booking without token | Authorization error | ✅ Passed |
> 💡 _Full test cases with detailed steps, inputs, expected results, actual result etc. are provided in the Excel file._

----------

### 🔐 Authentication Notes

-   Token is generated using `/auth` endpoint
    
-   Use the token as a `Cookie` header:
	> Cookie: token=<your_token_value>
- Required for `PUT`, `PATCH`, and `DELETE` operations

------------

### 🧾 Sample Request – Update Booking with Auth

**Endpoint:** `PUT https://restful-booker.herokuapp.com/booking/:id`  
**Headers:** 

    Cookie: token=abc123xyz
    Content-Type: application/json
**Body:**

    {
      "firstname": "Tanvir Jahan",
      "lastname": "Alin",
      "totalprice": 1200,
      "depositpaid": true,
      "bookingdates": {
        "checkin": "2024-01-01",
        "checkout": "2025-01-01"
      },
      "additionalneeds": "Breakfast"
    }

-------------

### 📈 Key Learnings

-   Hands-on experience in **API functional testing**
    
-   Understanding **CRUD operations and RESTful principles**
    
-   Working with **Postman collection runner and environment variables**
    
-   Writing clear **test cases and test documentation**
    
------

## 👩‍💻 Author

**Tanvir Jahan Alin**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tanvir-jahan-alin/)

---------

## 📎 References

- [Restful Booker API Documentation](https://restful-booker.herokuapp.com/apidoc/index.html)

------------
Thank you for reviewing this project!
