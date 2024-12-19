# Unhandled Error in Async Express.js Route

This repository demonstrates a common error in Node.js Express.js applications where errors during asynchronous operations are not properly handled, resulting in silent failures. The server doesn't respond with an appropriate error status code when an error occurs.

## Bug Description
The `bug.js` file contains an Express.js server with an asynchronous route.  This route uses promises but lacks robust error handling. If the asynchronous operation (`someAsyncOperation()`) throws an error, the error is logged to the console, but the client receives no response, leading to a poor user experience and difficulty in debugging.

## Solution
The `bugSolution.js` file provides a corrected version of the server. It uses a `try...catch` block within the async operation handler to catch potential errors.  The error is then handled appropriately by sending an error response to the client with a relevant HTTP status code (500 Internal Server Error).