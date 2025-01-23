# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by an incorrectly specified dependency array.  The counter component updates continuously instead of once per second.

## Bug Description
The `useEffect` hook is used to update the counter every second. However, the dependency array is empty (`[]`), which means the effect runs after every render, regardless of the counter's value. This creates a loop because each effect call updates the counter, triggering another render, and subsequently another effect call.  The solution is to include `count` in the dependency array.

## Bug Reproduction
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the rapidly incrementing counter.

## Solution
The solution involves adding `count` to the dependency array in the `useEffect` hook. This ensures the effect only runs when the `count` value changes.