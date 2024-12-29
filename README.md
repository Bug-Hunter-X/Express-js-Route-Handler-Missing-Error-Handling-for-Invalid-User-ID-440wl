# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the example shows a route that fetches a user by ID, but fails to handle cases where the ID is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  The handler attempts to parse the user ID as an integer using `parseInt()`, but doesn't check if the result is a valid integer. If the ID is not a number (e.g., a string), `parseInt()` will return `NaN`, causing the `users.find()` method to fail silently or throw an error, depending on the context.

## Solution

The `bugSolution.js` file provides a corrected version.  It includes error handling to check if the parsed ID is a number before attempting to find the user.  If the ID is invalid, it returns an appropriate HTTP error response.