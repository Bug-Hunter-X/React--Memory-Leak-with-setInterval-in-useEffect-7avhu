# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common React bug involving memory leaks caused by improper use of the `setInterval` function within the `useEffect` hook.

## Bug Description

The `MyComponent` component uses `setInterval` to update a counter every second. However, it fails to include a cleanup function in the `useEffect` hook. This leads to multiple intervals running concurrently whenever the component re-renders, causing a memory leak.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook that clears the interval using `clearInterval` when the component unmounts or when the dependency array changes.

## How to reproduce

1. Clone the repository
2. Run `npm install`
3. Run `npm start`
4. Observe the console for memory usage. You'll notice that it continues to increase while the component is active.