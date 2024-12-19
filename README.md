# Express.js Route Handler Bug: Missing Error Handling

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The provided `bug.js` file contains a route that attempts to access a user by ID. However, it fails to handle cases where the ID is not a valid integer, leading to potential errors.

The `bugSolution.js` file provides a corrected version with appropriate error handling to gracefully manage invalid input and prevent crashes.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install express` to install the required dependencies.
3. Run `node bug.js`.
4. Make a request to `/users/abc` (or any non-numeric ID).  You will likely see a server error.

## Solution

The solution involves adding input validation to ensure the user ID is a number before attempting to parse it.  This prevents the potential error caused by trying to parse a non-numeric string as an integer. The corrected code handles the invalid input gracefully, returning a 400 Bad Request status code.