# JavaScript Closure Gotcha in setTimeout

This repository demonstrates a common error involving closures and `setTimeout` in JavaScript. The `bug.js` file contains code that incorrectly uses a closure, leading to unexpected behavior. The `bugSolution.js` file provides a corrected version.

## Bug

The bug arises from how JavaScript handles closures and variable scope within asynchronous functions.  The `setTimeout` function creates a callback function which, when executed later, accesses the variable `i`. By the time these callbacks run, the loop has already completed, and `i` holds its final value of 10.

## Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures that each callback function has its own copy of `i`, preserving the intended behavior.