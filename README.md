# JavaScript Closure Bug

This repository demonstrates a common JavaScript bug related to closures and the `setTimeout` function within loops. The problem arises because the value of `i` is not captured correctly within the closure created by the `setTimeout` callback.

## Bug Description

The code creates a loop that uses `setTimeout` to log the value of `i` after a one-second delay.  Due to how closures work in JavaScript, the value of `i` is not captured at the time of the `setTimeout` call, but rather at the time the `setTimeout` callback is executed. By then, the loop has already completed and the final value of `i` is used for all iterations resulting in an unexpected output.

## How to Reproduce

1. Clone this repository.
2. Open `bug.js`.
3. Run the `myFunction()`.
4. Observe that the output shows 10 ten times instead of 0 to 9.

## Solution

The solution involves using an Immediately Invoked Function Expression (IIFE) or `let` to create a new scope for the variable 'i'. This ensures that the correct value of `i` is captured for each iteration.

See `bugSolution.js` for the corrected code.