# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving an infinite loop within a `useEffect` hook. The bug arises from updating the state based on the current state's value within the `useEffect`'s callback, creating an endless cycle.

## Bug Description

The `MyComponent` attempts to increment a counter only when its value is even.  This logic, placed within `useEffect` with `count` as a dependency, leads to an infinite rendering loop because any even number immediately triggers an increment, making it odd, and the next render makes it even again, and so on.

## Solution

The solution involves restructuring the update logic to avoid the dependency on the current state. We update the state in a way that doesn't trigger a loop. Instead, a button click explicitly manages state change.
