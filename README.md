# React 19 useEffect setInterval Memory Leak

This repository demonstrates a common error in React 19 applications: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to memory leaks because the interval continues to run even after the component unmounts.

## Problem

The `bug.js` file contains code that uses `setInterval` to update a counter every second.  However, it lacks the necessary cleanup function to stop the interval when the component unmounts. This results in the interval continuing to run indefinitely, consuming memory and potentially impacting performance.

## Solution

The `bugSolution.js` file provides a corrected version.  It uses the return value of `useEffect` to provide a cleanup function that clears the interval when the component unmounts, preventing the memory leak.