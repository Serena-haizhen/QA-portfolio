# API Test Ideas

## POST Create Booking - Basic Test Ideas

1. Valid data  
Submit complete and correct booking data. The system should create a booking successfully.

2. Missing required field  
If a required field is missing, the system should reject the request or return a proper error result.

3. Wrong data type  
If a field that should be a number or boolean is submitted as a string or another wrong type, the system should handle it correctly.

4. Empty value  
If a field is submitted with an empty value, the system should respond according to the expected validation rules.

5. Extreme value  
If very long strings, very large numbers, or boundary date values are submitted, the system should handle them safely and consistently.
