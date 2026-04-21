# HTTP and Basic API Notes for QA

## What I learned
I learned the basic ideas of HTTP and API testing for QA.

## HTTP Basics
- A browser sends a request to the server
- The server sends a response back
- GET is used to get data
- POST is used to submit data

## Common Status Codes
- 200 = success
- 400 = bad request
- 401 = not authenticated
- 403 = authenticated but no permission
- 404 = not found
- 500 = internal server error

## Login Flow Basics
- After clicking login, the browser usually sends a POST request
- The server checks the username and password
- If login succeeds, the system creates a login state
- If login fails, the system returns an error result

## Cookie, Session and Token
- Cookie is small information stored in the browser
- Session helps the system remember that the user has logged in
- Token is a credential used to prove user identity

## UI Testing vs API Testing
- UI testing checks visible page behavior
- API testing checks backend interface behavior and data transfer

## Postman Basics
- Postman can send API requests directly
- I sent my first GET request in Postman
- I received a 200 OK response and JSON data

## Why this matters for QA
A QA should not only say that something failed on the page.
A stronger QA should also understand request, response, API behavior, and where the issue is more likely to happen.
