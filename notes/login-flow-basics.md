# Login Flow Basics

## What happens after clicking login
1. The browser collects the username and password
2. The browser sends a request to the server
3. The request is usually a POST request
4. The server checks the login information
5. The server returns a result
6. If successful, the system creates a login state
7. The page redirects or shows an error message

## Why login usually uses POST
Login usually uses POST because the user is submitting information, not only getting information.

## Why cookie, session, or token is needed
The system needs to remember that the user has already logged in, so the user does not need to log in again on every page.

## Where login problems may happen
- Invalid input
- Request or server processing failure
- Incorrect page feedback or redirect behavior

## Why QA should think this way
QA should not only see the surface result.
QA should think about whether the issue is more likely in the input, request handling, or page behavior.
