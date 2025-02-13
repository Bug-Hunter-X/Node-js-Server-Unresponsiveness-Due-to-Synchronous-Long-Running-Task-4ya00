# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications where a long-running synchronous operation blocks the event loop, causing the server to hang or become unresponsive. The bug.js file contains the problematic code, while bugSolution.js provides a solution using asynchronous operations.

## Problem

The `bug.js` file contains a simple HTTP server.  However, it includes a `while` loop that simulates a long-running task. This synchronous task blocks the event loop, preventing the server from responding to other requests or even shutting down gracefully.  This is a common pitfall when performing I/O-bound or CPU-bound operations without proper asynchronous handling. 

## Solution

The `bugSolution.js` file demonstrates how to solve this problem by using asynchronous techniques.  Instead of performing the long-running task synchronously, we use `setTimeout` to offload the work to the event loop, allowing the server to continue processing other requests.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Open a browser and try to access `http://localhost:3000`.  You'll likely observe a delay or unresponsiveness.
5. Run `node bugSolution.js` and repeat step 4. You should see a prompt response.

## Lessons Learned

This example highlights the importance of asynchronous programming in Node.js to prevent blocking the event loop and maintain application responsiveness.