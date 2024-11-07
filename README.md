# Backend Repository Documentation

## 1. Backend Lambda Function: `lambda_function.py`

### Purpose
Contains the main Lambda function code that interfaces with an AWS DynamoDB table to update and retrieve the visitor count for the Cloud Resume Challenge.

### Overview
- **AWS Integration**: Connects to the `visitor_count` DynamoDB table and increments the visitor count for the `index.html` path.
- **Response**: Returns a `200` status code with the updated count and includes CORS headers for cross-origin access.

---

## 2. Tests Folder

### Purpose
Holds unit and system tests to validate the backend functionality and ensure reliable operation.

### Key Files
#### 1. `__init__.py`
- Marks the `tests` directory as a Python package.

#### 2. `test_lambda_unit.py`
- **Purpose**: Contains unit tests that use `pytest` and `moto` to mock the AWS DynamoDB environment.
- **Functionality**: Validates the Lambda function’s behavior for updating and retrieving visitor counts.
- **Details**: Tests the logic by simulating DynamoDB operations to ensure correctness without accessing real AWS resources.

#### 3. `test_visitor_counter_system.py`
- **Purpose**: A system test using `requests` to verify the end-to-end functionality of the deployed API.
- **Checks**: Confirms HTTP status codes, CORS headers, and the correct incrementing of the visitor count after API calls.
- **Details**: Simulates real requests to the API to verify complete operation from the client’s perspective.

#### 4. `test_cloud_resume_e2e.py`
- **Purpose**: Conducts an end-to-end test using Playwright for browser automation.
- **Functionality**: Validates that the frontend correctly displays and updates the visitor count after interacting with the backend.
- **Details**: Checks for the presence and visibility of specific content and verifies that the visitor count increments after a page refresh.

---

## 3. `.gitignore` File

The `.gitignore` file in the backend project specifies which files and directories should be ignored by Git to keep the repository clean and secure. 
- Ignores Python bytecode and temporary compiled files.
- Prevents sensitive files and project-specific configurations from being included.
- Ignores log files and test coverage reports that are not essential for code versioning.

---

## 4. `__init__.py` File

### Purpose
Included in both the `backend` and `tests` directories to ensure Python treats these folders as packages, enabling module recognition and importing.
