# Task 5 – API Testing and Validation using Postman

This project tests and validates the Flask-based MNIST Deep Learning API from Task 4.

## Test Cases

| Test Case | Method | Endpoint | Expected |
|---|---|---|---|
| TC-01 API Health Check | GET | / | 200 OK |
| TC-02 Valid Prediction | POST | /predict | 200 OK |
| TC-03 Missing Input Data | POST | /predict | 400 Bad Request |
| TC-04 Incorrect Pixel Count | POST | /predict | 400 Bad Request |

## Automated Assertions

The Postman collection validates HTTP status, response status, predicted digit range, confidence range, missing input validation, and the 784-pixel validation.

## How to Run

1. Start the Flask API with `python app.py`.
2. Confirm `http://127.0.0.1:5000` is running.
3. Import `Postman_Collection.json` into Postman.
4. Run the requests individually or run the complete collection.
5. Verify the Postman Test Results.

## Expected Result

- TC-01: 3/3 passed
- TC-02: 4/4 passed
- TC-03: 3/3 passed
- TC-04: 3/3 passed
- Overall: **13/13 assertions passed, 0 errors**

## Error Responses

Missing input:
```json
{"message":"Missing 'input_data' field","status":"error"}
```

Incorrect pixel count:
```json
{"message":"input_data must contain exactly 784 pixel values","status":"error"}
```

## Project Structure

```text
Task_5_API_Testing/
├── Postman_Collection.json
├── README.md
├── test_results/
│   └── Postman_Test_Results.txt
└── screenshots/
    └── README.md
```
