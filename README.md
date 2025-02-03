# React Native useEffect Stale Closure Bug

This repository demonstrates a common bug in React Native applications involving the `useEffect` hook and stale closures.  The bug arises from incorrectly specifying the dependencies within the `useEffect` hook's dependency array.  The solution shows how to correctly handle the dependencies to avoid this issue. 

## Bug
The original code attempts to log the value of `props.someProp` inside the `useEffect` hook.  However, because `props.someProp` is not included in the dependency array, the effect only runs once on mount and doesn't update when `props.someProp` changes. This results in stale closure, using the initial value of `someProp` even when it's updated by the parent component. 

## Solution
The solution demonstrates the correct way to use `useEffect`, ensuring that the effect re-runs whenever `props.someProp` changes by including it in the dependency array.