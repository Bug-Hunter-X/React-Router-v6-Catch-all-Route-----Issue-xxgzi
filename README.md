# React Router v6 Catch-all Route '*' Issue

This repository demonstrates a common issue encountered when using catch-all routes ('*') in React Router v6.  The problem arises when the catch-all route is placed after more specific routes. This leads to the catch-all route not correctly handling unmatched paths, resulting in unexpected rendering or errors.

## Problem

The provided `App.js` demonstrates the issue.  The catch-all route (`/*`) is defined after routes for '/' and '/about'.  In this setup, the catch-all route will *never* be activated, even if you navigate to a path that doesn't match any other route.  This is because React Router v6 matches routes in order, and the first match is used.  This leads to the `NotFound` component never being rendered. 

## Solution

`AppSolution.js` provides the solution.  The correct approach is to always place the catch-all route at the very end of your route definitions.  This ensures that it will only be used when no other routes match the current URL.