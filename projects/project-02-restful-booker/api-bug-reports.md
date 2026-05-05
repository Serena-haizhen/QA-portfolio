# Restful-Booker API Bug Reports

This document contains API bug reports found during negative testing of the Restful-Booker `POST /booking` endpoint.

## Scope

- Application under test: Restful-Booker API
- Endpoint tested: `POST /booking`
- Tool used: Postman
- Test focus: request body validation, data type validation, and error handling

## Summary of Findings

| ID | Title | Severity | Status |
|---|---|---|---|
| BUG-API-001 | Missing required fields return `500 Internal Server Error` | Medium | Open |
| BUG-API-002 | Invalid `totalprice` type is accepted and stored as `null` | Medium | Open |
| BUG-API-003 | Invalid `depositpaid` type is accepted and converted to `true` | Low | Open |

---

## BUG-API-001 - POST /booking returns 500 when required fields are missing

### Summary

`POST /booking` returns `500 Internal Server Error` when required fields such as `firstname`, `lastname`, or `bookingdates` are missing.

### Environment

- API: Restful-Booker
- Endpoint: `POST https://restful-booker.herokuapp.com/booking`
- Tool: Postman
- Header: `Content-Type: application/json`

### Severity

Medium

### Priority

Medium

### Steps to Reproduce

1. Send a `POST` request to `https://restful-booker.herokuapp.com/booking`.
2. Set header `Content-Type` to `application/json`.
3. Use a JSON body with one required field removed, for example remove `firstname`.
4. Click `Send`.

### Example Request Body

```json
{
  "lastname": "Brown",
  "totalprice": 111,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2018-01-01",
    "checkout": "2019-01-01"
  },
  "additionalneeds": "Breakfast"
}
```

### Expected Result

The API should reject the invalid request with a clear client error response, such as `400 Bad Request`, and return a useful validation message.

Example:

```json
{
  "error": "firstname is required"
}
```

### Actual Result

The API returns:

```text
500 Internal Server Error
```

Response body:

```text
Internal Server Error
```

### Impact

Invalid client input causes a server error instead of a clear validation response. This makes the API harder to debug and suggests weak error handling for missing required fields.

---

## BUG-API-002 - POST /booking accepts invalid totalprice type and stores null

### Summary

`POST /booking` accepts a string value for `totalprice` and creates a booking with `totalprice` stored as `null`.

### Environment

- API: Restful-Booker
- Endpoint: `POST https://restful-booker.herokuapp.com/booking`
- Tool: Postman
- Header: `Content-Type: application/json`

### Severity

Medium

### Priority

Medium

### Steps to Reproduce

1. Send a `POST` request to `https://restful-booker.herokuapp.com/booking`.
2. Set header `Content-Type` to `application/json`.
3. Set `totalprice` to a string value such as `"abc"`.
4. Click `Send`.

### Example Request Body

```json
{
  "firstname": "Jim",
  "lastname": "Brown",
  "totalprice": "abc",
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2018-01-01",
    "checkout": "2019-01-01"
  },
  "additionalneeds": "Breakfast"
}
```

### Expected Result

The API should reject the invalid data type with a clear `4xx` validation error.

### Actual Result

The API returns `200 OK` and creates a booking.

The response body contains:

```json
"totalprice": null
```

### Impact

The API accepts invalid data and stores an incomplete value. This may cause bad booking data and downstream issues in reporting, payment, or validation logic.

---

## BUG-API-003 - POST /booking accepts string value for depositpaid and converts it to true

### Summary

`POST /booking` accepts a string value for the boolean field `depositpaid` and converts it to `true`.

### Environment

- API: Restful-Booker
- Endpoint: `POST https://restful-booker.herokuapp.com/booking`
- Tool: Postman
- Header: `Content-Type: application/json`

### Severity

Low

### Priority

Medium

### Steps to Reproduce

1. Send a `POST` request to `https://restful-booker.herokuapp.com/booking`.
2. Set header `Content-Type` to `application/json`.
3. Set `depositpaid` to a string value such as `"yes"`.
4. Click `Send`.

### Example Request Body

```json
{
  "firstname": "Jim",
  "lastname": "Brown",
  "totalprice": 111,
  "depositpaid": "yes",
  "bookingdates": {
    "checkin": "2018-01-01",
    "checkout": "2019-01-01"
  },
  "additionalneeds": "Breakfast"
}
```

### Expected Result

The API should reject the invalid data type with a clear `4xx` validation error, unless this conversion is explicitly documented.

### Actual Result

The API returns `200 OK` and creates a booking.

The response body contains:

```json
"depositpaid": true
```

### Impact

The API silently converts invalid input instead of validating it strictly. This may hide client-side data issues and create inconsistent behavior.
