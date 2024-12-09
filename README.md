# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug creates an infinite render loop because the state update is performed within the `useEffect` which has an empty dependency array [] leading to it being called in every render causing a continuous state update.

## Bug Description
The `MyComponent` component uses `useEffect` to update the `count` state. However, because the `useEffect` hook's dependency array is empty (`[]`), it runs after every render, leading to a continuous state update and an infinite loop. The application will likely crash or become unresponsive. 

## Solution
The solution involves correctly managing the dependencies in the `useEffect` hook.  Adding 'count' to the dependency array will make the effect only run when the value of 'count' changes and resolve the infinite loop. 