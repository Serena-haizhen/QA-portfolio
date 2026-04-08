# Login Test Cases

## LOGIN-001

**Title:** Login with valid username and valid password

**Preconditions:**
- The login page is available
- A valid username and password exist

**Steps:**
1. Open the login page
2. Enter a valid username
3. Enter a valid password
4. Click the Login button

**Expected Result:**
1. The user is logged in successfully
2. The user is redirected to the dashboard

**Actual Result:**
1. The user is not logged in
2. An unknown error message is displayed
3. The user remains on the login page

**Status:** Fail

---

## LOGIN-002

**Title:** Login with invalid username and valid password

**Preconditions:**
- The login page is available
- A valid password exists

**Steps:**
1. Open the login page
2. Enter an invalid username
3. Enter a valid password
4. Click the Login button

**Expected Result:**
1. The system blocks the login attempt
2. An error message is displayed
3. The user remains on the login page

**Actual Result:**
1. The system blocks the login attempt
2. An error message is displayed
3. The user remains on the login page

**Status:** Pass

---

## LOGIN-003

**Title:** Login with a valid username and an invalid password

**Preconditions:**
- The login page is accessible
- A valid username exists in the system

**Steps:**
1. Open the login page
2. Enter a valid username
3. Enter an invalid password
4. Click the Login button

**Expected Result:**
1. Access to the system is denied
2. An error message is displayed
3. The user remains on the login page

**Actual Result:**
1. Access to the system is denied
2. An error message is displayed
3. The user remains on the login page

**Status:** Pass

---

## LOGIN-004

**Title:** Login with an invalid username and an invalid password

**Preconditions:**
- The login page is accessible

**Steps:**
1. Open the login page
2. Enter an invalid username
3. Enter an invalid password
4. Click the Login button

**Expected Result:**
1. Access to the system is denied
2. An error message is displayed
3. The user remains on the login page

**Actual Result:**
1. Access to the system is denied
2. An error message is displayed
3. The user remains on the login page

**Status:** Pass

---

## LOGIN-005

**Title:** Login with empty username

**Preconditions:**
- The login page is accessible

**Steps:**
1. Open the login page
2. Leave the username field empty
3. Enter a valid password
4. Click the Login button

**Expected Result:**
1. A validation message is displayed
2. Access to the system is denied
3. The user remains on the login page

**Actual Result:**
1. A validation message is displayed
2. Access to the system is denied
3. The user remains on the login page

**Status:** Pass

---

## LOGIN-006

**Title:** Login with empty password

**Preconditions:**
- The login page is accessible

**Steps:**
1. Open the login page
2. Enter a valid username
3. Leave the password field empty
4. Click the Login button

**Expected Result:**
1. A validation message is displayed
2. Access to the system is denied
3. The user remains on the login page

**Actual Result:**
1. The user successfully accesses the system
2. The user is redirected to the dashboard

**Status:** Fail
