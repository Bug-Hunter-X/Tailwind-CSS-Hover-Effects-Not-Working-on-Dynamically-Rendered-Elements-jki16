# Tailwind CSS Hover Effects Bug

This repository demonstrates an uncommon bug in Tailwind CSS where hover effects fail to work correctly on dynamically rendered elements.  The issue is specifically related to the timing of the element's rendering and the application of Tailwind's styles.

## Problem Description

The provided `bug.js` file contains a simple React component with a button. This button has a Tailwind CSS class that applies a hover effect.  However, the hover effect only activates *after* the component rerenders.  The initial render displays the button without the hover functionality.

## Solution

The solution, demonstrated in `bugSolution.js`, involves using the `useLayoutEffect` hook to ensure that the Tailwind classes are applied before the browser's layout calculations are complete. This guarantees that the hover styles are applied and correctly take effect immediately.

This issue highlights a scenario where Tailwind's declarative styling approach interacts with the runtime behavior of a React application, requiring a bit more proactive handling to ensure proper behavior. 