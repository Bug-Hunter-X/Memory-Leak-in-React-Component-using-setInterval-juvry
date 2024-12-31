# React setInterval Memory Leak
This repository demonstrates a common mistake when using the `setInterval` function within a React component's `useEffect` hook, which leads to a memory leak.  The problem arises from the lack of a cleanup function to stop the interval when the component unmounts.

## Bug Description
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it omits the essential cleanup function in the `useEffect` hook's return value. This results in multiple `setInterval` instances running simultaneously when the component re-renders, consuming unnecessary memory and potentially leading to performance issues.

## Solution
The `bugSolution.js` file presents the corrected code. The solution incorporates a cleanup function returned by the `useEffect` hook, ensuring that the interval is cleared when the component unmounts or when the dependency array changes, thus preventing memory leaks.  This best practice avoids unnecessary resource consumption.
