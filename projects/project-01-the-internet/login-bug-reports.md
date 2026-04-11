# Login Bug Reports

## BUG-001

**Summary:** User cannot log in with valid credentials.

**Environment:** Windows 11, Chrome, Login page

**Steps to Reproduce:**
1. Open the login page.
2. Enter a valid username.
3. Enter a valid password.
4. Click the login button.

**Expected Result:**
1. The user should log in successfully.
2. The user should be redirected to the dashboard.

**Actual Result:**
1. The user remains on the login page.
2. An unknown error message is displayed.
3. The user is not logged in.

**Severity:** High  
**Priority:** High

---

## BUG-002

**Summary:** The user is able to log in even when the password field is empty.

**Environment:** Windows 11, Chrome, Login page

**Steps to Reproduce:**
1. Open the login page.
2. Enter a valid username.
3. Leave the password field empty.
4. Click the login button.

**Expected Result:**
1. The user should not be able to log in.
2. The user should remain on the login page.
3. A validation message should be displayed.

**Actual Result:**
1. The user logs in successfully.
2. The user is redirected to the dashboard.

**Severity:** High  
**Priority:** High
