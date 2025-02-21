# Unresponsive Node.js Server

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The `server.js` file includes a `while` loop that simulates a long-running task.  This loop blocks the Node.js event loop, preventing the server from responding to subsequent requests.  If you try to access the server while this loop is running, it will appear unresponsive.

## Solution

The `serverSolution.js` file demonstrates a solution using asynchronous operations.  Instead of blocking the event loop, it offloads the long-running task using `setTimeout`.  This allows the event loop to continue processing other requests, keeping the server responsive.

## How to Run

1. Clone the repository
2. Navigate to the directory in your terminal
3. Run `node server.js` (for the buggy code) or `node serverSolution.js` (for the solution) 
4. Test the server by accessing it in your browser or using a tool like `curl`.