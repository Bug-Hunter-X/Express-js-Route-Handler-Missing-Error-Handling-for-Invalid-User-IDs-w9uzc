# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  failure to handle invalid or missing parameters, specifically focusing on user IDs.  The provided code attempts to access a user based on an ID provided in the URL, but doesn't handle cases where the ID is invalid (not a number) or doesn't exist, resulting in an application crash or unexpected behavior.

## Bug

The `bug.js` file contains the buggy code.  It attempts to parse the `userId` as an integer and then uses it to find a user in an array.  However, if `userId` is not a number, `parseInt(userId)` will return `NaN`, leading to issues in the `find` method.  Further, if no user is found, there's no appropriate error handling for this condition. 

## Solution

The `bugSolution.js` file presents a corrected version. It includes robust error handling, checking for invalid input types and nonexistent users, providing proper HTTP status codes and error messages.