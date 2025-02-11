# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: a memory leak caused by improper use of `setInterval` within the `useEffect` hook.  The provided `bug.js` file showcases the incorrect implementation, while `bugSolution.js` offers the corrected version.

The issue arises because the `setInterval` function, once started, continues to run indefinitely unless explicitly stopped.  Without cleanup, this creates a memory leak, as the component continues to hold a reference to the interval, preventing garbage collection.

The solution involves using the return value of `useEffect` to implement a cleanup function that clears the interval before the component unmounts or when the dependency array changes.