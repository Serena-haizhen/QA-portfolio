# POST Create Booking

## Request
- Method: POST
- URL: https://restful-booker.herokuapp.com/booking

## Request Body
```json
{
  "firstname": "Jim",
  "lastname": "Brown",
  "totalprice": 111,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2025-09-01",
    "checkout": "2025-09-05"
  },
  "additionalneeds": "Breakfast"
}
