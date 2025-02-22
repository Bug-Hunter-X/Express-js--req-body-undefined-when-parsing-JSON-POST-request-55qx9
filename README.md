# Express.js: req.body undefined when parsing JSON POST request

This repository demonstrates a common issue in Express.js applications where `req.body` is undefined when attempting to parse a JSON POST request.  The problem arises from improper or missing middleware configuration.

## Problem

The provided `bug.js` file showcases an Express.js application that's supposed to receive JSON data through a POST request to `/data`. However, due to a missing crucial middleware component, `req.body` remains undefined, leading to unexpected behavior or errors.

## Solution

The `bugSolution.js` file corrects this issue by incorporating the `express.json()` middleware. This middleware parses incoming requests with JSON payloads and populates the `req.body` object accordingly.

## How to reproduce the bug

1. Clone this repository.
2. Run `bug.js` using Node.js.
3. Send a POST request to `http://localhost:3000/data` with a JSON payload (e.g., using Postman or curl).
4. Observe that the server receives the request but logs an empty `req.body`.

## How to fix the bug

1. Refer to `bugSolution.js`.
2. Notice that `express.json()` middleware is added before the route handler.  This ensures that JSON data is parsed before it's accessed.
3. Re-run the application and send the POST request again.  This time `req.body` will contain the expected JSON data.

This example highlights the importance of correctly configuring middleware in Express.js applications to handle various request types and data formats.