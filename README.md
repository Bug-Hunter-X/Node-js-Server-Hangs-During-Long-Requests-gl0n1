# Node.js Server Hanging Issue

This repository demonstrates a common issue in Node.js where a long-running request can cause the server to hang.  The problem arises because Node.js uses a single-threaded event loop.  If a request blocks this loop for an extended period, other requests are unable to be processed, resulting in an unresponsive server.

The `server.js` file contains the buggy code, while `server-solution.js` provides a solution using asynchronous operations.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node server.js`.
4. Make a request to `http://localhost:3000`. You'll notice that subsequent requests will not be processed until the initial request completes.

## Solution

The solution utilizes asynchronous operations or worker threads to prevent blocking the event loop. The `server-solution.js` file demonstrates this.