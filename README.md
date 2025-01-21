# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  the lack of error handling when processing parameters. Specifically, the `/users/:id` route fails to handle cases where `req.params.id` is not a valid integer.

## Bug

The `bug.js` file shows the problematic code.  It attempts to parse `req.params.id` as an integer and then uses it to find a user. However, if `req.params.id` is not a number (e.g., a string or undefined), `parseInt(userId)` will return `NaN`, leading to a failure to find the user and potentially causing an unhandled exception or unexpected behavior.

## Solution

The `bugSolution.js` file provides a corrected version. It includes checks to ensure `req.params.id` is a valid number before attempting to parse and use it.  This prevents errors and provides better error handling to the client.