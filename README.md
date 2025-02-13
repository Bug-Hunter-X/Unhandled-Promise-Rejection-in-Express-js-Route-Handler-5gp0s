# Unhandled Promise Rejection in Express.js

This repository demonstrates a common error in Express.js applications: failure to properly handle rejected Promises in asynchronous route handlers.  When an asynchronous operation within a route fails, without proper error handling, the application might crash or behave unexpectedly, resulting in a 500 Internal Server Error.

The `bug.js` file shows an example of this error, while `bugSolution.js` provides the correct implementation with proper error handling.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `node bug.js`.
4. Observe that sometimes the server returns a 'Success!' response, and sometimes it crashes without providing any useful error message.
5. Run `node bugSolution.js` to see the fixed version.

## Solution

Properly handling Promise rejections is crucial for robustness. Always use `.catch()` to gracefully handle errors, either sending a client-side error response, logging the error for debugging, or taking other appropriate recovery actions. 