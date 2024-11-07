# Project Repository Documentation

## 1. Backend Lambda Function: `lambda_function.py`

### Purpose
Contains the main Lambda function code that interfaces with an AWS DynamoDB table to update and retrieve the visitor count for the Cloud Resume Challenge.

### Overview
- **AWS Integration**:
  - Connects to the `visitor_count` DynamoDB table.
  - Increments the visitor count for the `index.html` path.
- **Response**:
  - Returns a `200` status code with the updated count.
  - Includes CORS headers for cross-origin access.

---

## 2. Tests Folder

**Location**: `tests`

### Purpose
Holds unit and system tests to validate the backend functionality and ensure reliable operation.

### Key Files
#### 1. `__init__.py`
- Marks the `tests` directory as a Python package.

#### 2. `test_lambda_unit.py`
- **Purpose**: Contains unit tests that use `pytest` and `moto` to mock the AWS DynamoDB environment.
- **Functionality**:
  - Validates the Lambda function’s behavior for updating and retrieving visitor counts.

#### 3. `test_visitor_counter_system.py`
- **Purpose**: A system test using `requests` to verify the end-to-end functionality of the deployed API.
- **Checks**:
  - Status codes, CORS headers, and visitor count incrementation.

### Testing Highlights
- **Unit Tests**:
  - Ensure the Lambda function updates and retrieves counts correctly.
- **System Tests**:
  - Simulate real-world API interactions to confirm complete functionality.

---

## 3. End-to-End Test: `test_cloud_resume_e2e.py`

**Location**: `test_cloud_resume_e2e.py`

### Purpose
Performs an end-to-end test using Playwright for browser automation to validate the complete visitor count functionality on the resume page.

### Test Process
#### 1. Navigation
- Opens the resume webpage in a browser.

#### 2. Assertions
- Verifies the visibility of the H1 heading and specific text.
- Checks that the initial and updated visitor counts are valid integers.

#### 3. Logging
- Utilizes Python’s `logging` module for detailed test execution output.

### Key Features
- Captures the visitor count, refreshes the page, and verifies the increment.
- Closes the browser after completion to ensure clean test runs.

---

## 4. `__init__.py` File

**Location**: `backend` and `tests` directories

### Purpose
Included in both the `backend` and `tests` directories to ensure Python treats these folders as packages, enabling module recognition and importing.
