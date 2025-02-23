# useEffect Runs After Every Render in React 19 Despite Dependencies

This repository demonstrates an unusual behavior observed in React 19 where the `useEffect` hook runs after every render, regardless of the dependencies array. This can lead to performance issues and unexpected side effects.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides a solution to address this behavior.

## Problem

The `useEffect` hook in the provided code is intended to log the current count only when the count changes. However, in React 19, it appears to run every single time the component renders.  This is inefficient and can lead to unwanted behavior.

## Solution

This problem usually stems from missing or incorrectly specified dependencies in the useEffect's second argument.  The solution involves ensuring the dependency array contains all state variables or props used within the effect.  If the effect should run only once after the initial render, an empty array `[]` is appropriate.