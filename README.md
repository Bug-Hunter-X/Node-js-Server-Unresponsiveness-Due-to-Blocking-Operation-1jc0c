# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation that blocks the event loop.  The `server.js` file contains a server that performs a 5-second CPU-bound operation, preventing it from handling other requests during that time. The `serverSolution.js` file shows how to fix this using asynchronous operations.

## Bug

The bug lies in the synchronous `while` loop within the request handler.  This loop occupies the event loop, preventing Node.js from processing other requests or events. This results in a server that appears to hang or become unresponsive while the loop is executing.

## Solution

The solution involves refactoring the code to utilize asynchronous operations.  This allows the event loop to remain responsive while long-running tasks are handled concurrently without blocking.