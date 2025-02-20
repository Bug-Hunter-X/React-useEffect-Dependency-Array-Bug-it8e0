# React useEffect Dependency Array Bug

This repository demonstrates a common bug in React's `useEffect` hook:  incorrectly specifying the dependency array.  The example showcases how failing to include relevant state variables within the dependency array leads to unexpected behavior and performance issues.

## The Problem

The provided `MyComponent` uses `useEffect` to log the component's render count and perform cleanup.  However, the initial implementation lacks `count` in the dependency array. This means the effect runs after *every* render, regardless of whether `count` has changed.  This can cause excessive re-renders and unnecessary console output, especially when the `count` is updated frequently.

## The Solution

The solution involves correctly including `count` within the dependency array: `[count]`. This ensures the effect only runs when the value of `count` changes, optimizing performance and preventing unwanted side effects.