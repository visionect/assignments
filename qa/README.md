# QA Engineer Assignment: Login Test with Playwright, Python, and Docker

## Objective
Create an automated test using Playwright and Python to verify the login functionality of https://my.getjoan.com/. The test should be containerized using Docker for easy deployment and execution.

## Requirements

### 1. Test Case
Implement a test case that does the following:
- Navigate to https://my.getjoan.com/
- Enter the email address "test@example.com" and password "123" into the email/password input box.
- Click the "Sign in with email" button
- Verify that login fails and the message "* Please enter a correct email address and password. Note that both fields may be case-sensitive.".

#### 1.1 Details
- Implement parameterized tests to check multiple email addresses
- Add screenshots or video recording of failed tests
- Implement a simple HTML report generator for test results

### 2. Technology Stack
- Playwright
- Python
- Docker

### 3. Implementation Details
- Use Playwright's Python API to interact with the web page
- Implement appropriate wait strategies to ensure elements are loaded before interacting with them
- Use assertions to verify the presence of the error message
- Implement proper error handling and logging
- Follow PEP 8 style guidelines for Python code

### 4. Docker Integration
- Use the provided Dockerfile and set up the environment necessary to run the test
- Provide clear instructions on how to build and run the Docker container

### 5. Documentation
- Include a INSTRUCTIONS.md file with:
  - A brief explanation of the test case
  - Instructions for setting up and running the test both locally and using Docker
  - Any assumptions or limitations of the current implementation
  - Suggestions for potential improvements or extensions to the test suite

### 6. Bonus Points (Optional)


## Deliverables
- Python script(s) containing the Playwright test
- INSTRUCTIONS.md with documentation
- Any additional configuration files or dependencies

## Evaluation Criteria
- Correctness of the test implementation
- Code quality and adherence to best practices
- Effective use of Playwright features
- Proper integration with Docker
- Quality and clarity of documentation
- Handling of edge cases and error scenarios
