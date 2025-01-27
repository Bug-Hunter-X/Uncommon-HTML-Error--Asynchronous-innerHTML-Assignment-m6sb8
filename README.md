# Uncommon HTML Error: Asynchronous innerHTML Assignment

This repository demonstrates an uncommon error that can occur when using `innerHTML` with asynchronous operations in JavaScript within an HTML context. The bug involves directly assigning the result of a function call that returns a Promise to `innerHTML`, which often results in unexpected behavior or errors.  The solution shows the correct way to handle asynchronous operations when updating the DOM.

## Bug

The `bug.html` file showcases the problematic code.  The `getDynamicContent` function simulates an asynchronous operation (like fetching data from a server).  The `innerHTML` property is incorrectly set directly to this function's result. Since the function returns a promise, it doesn't immediately provide the HTML string; the `innerHTML` becomes undefined, causing the failure.

## Solution

The `bugSolution.html` file shows the corrected approach.  It utilizes `.then()` to handle the resolved promise, updating `innerHTML` with the dynamic content once the promise is fulfilled.