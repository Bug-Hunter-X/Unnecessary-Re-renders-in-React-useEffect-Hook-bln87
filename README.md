# Unnecessary Re-renders in React useEffect Hook

This example demonstrates an uncommon bug in React involving the `useEffect` hook. The issue arises from an incorrectly defined dependency array, leading to unnecessary component re-renders.

## Problem

The provided `MyComponent` uses `useEffect` to log a message to the console every time the component renders.  However, the dependency array `[count]` means that the effect will run whenever the `count` state variable changes.

This is inefficient because the logging is not actually tied to any asynchronous operation or side effect that needs to happen only after the count changes; it simply logs a message each time the component updates, which is frequent and unnecessary.

## Solution

The solution involves removing `count` from the dependency array.  An empty array `[]` indicates that the effect should only run once after the initial render. If you need the effect to run conditionally, add the appropriate dependencies.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the console messages and the frequent updates.