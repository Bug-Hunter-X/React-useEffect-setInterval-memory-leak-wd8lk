# React useEffect setInterval Memory Leak
This repository demonstrates a common bug in React applications involving the improper use of `setInterval` within the `useEffect` hook, leading to memory leaks.  The `bug.js` file shows the problematic code, and `bugSolution.js` provides the corrected version.

The issue arises when `setInterval` is used without a mechanism to clear the interval when the component unmounts.  This results in the interval continuing to run even after the component is no longer needed, leading to wasted resources and potential memory leaks. The solution involves returning a cleanup function from `useEffect` to clear the interval.

## How to reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the continuously incrementing counter.
5. Note that the counter will continue to increment even after the component is unmounted (e.g., by navigating away from the page).