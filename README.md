# Unexpected Output in setTimeout Loop

This repository demonstrates a common closure-related issue in JavaScript when using `setTimeout` within a loop. The code appears to iterate 10 times, logging the numbers 0 through 9 with a one-second delay. However, the actual output is 10 ten times due to the asynchronous nature of `setTimeout` and how variables are captured in closures.

## Bug Description
The issue lies in how JavaScript handles closures. By the time `setTimeout` finally executes its callback, the loop has already completed and the value of `i` is 10. Thus, all callbacks log the final value of `i`. 

## Solution
The solution involves creating a new scope for each iteration using an Immediately Invoked Function Expression (IIFE) or by using `let` which has block scope.