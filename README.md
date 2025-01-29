# React useEffect Hook Missing Dependency

This repository demonstrates a common error in React applications: forgetting to include all necessary variables in the dependency array of the `useEffect` hook.  This can lead to unexpected behavior, including infinite loops and incorrect state updates.

The `bug.js` file shows the problematic code.  The `bugSolution.js` file provides the corrected version.

## Bug
The `useEffect` hook in `bug.js` attempts to log the current value of `count` after every render. However, the dependency array is empty (`[]`). This means the effect runs after *every* render, including those caused by the effect itself, creating an infinite loop.

## Solution
The `bugSolution.js` file corrects this by including `count` in the dependency array. The effect now only runs when the `count` variable changes.