# React setInterval Memory Leak
This example demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook.  Without proper cleanup, this leads to memory leaks as the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file shows the problematic code.  The `setInterval` function is called within `useEffect`, but lacks a return function to clear the interval when the component unmounts.

## Solution
The `bugSolution.js` file demonstrates the corrected code.  The return value of `useEffect` now includes a cleanup function that uses `clearInterval` to stop the interval when the component is no longer needed.