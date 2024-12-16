# React Native AsyncStorage Data Corruption Bug

This repository demonstrates a common, yet subtle, bug in React Native applications involving the use of AsyncStorage for data persistence. The issue stems from the asynchronous nature of AsyncStorage operations and the potential for race conditions when multiple concurrent operations are performed.

## Problem Description
When multiple `AsyncStorage.setItem` and `AsyncStorage.getItem` calls are executed concurrently, there's a risk that operations might overlap, leading to unexpected data overwrites or inconsistent data retrieval. The asynchronous nature of these calls makes identifying and debugging this type of bug particularly challenging.

## Reproducing the Bug
The `bug.js` file contains code that replicates the issue.  Run the application and observe the console output.  You'll likely see that the value retrieved from AsyncStorage is not always consistent with what was previously set.

## Solution
The solution provided in `bugSolution.js` addresses this by using Promises and `Promise.all` to ensure all operations complete before proceeding.  This prevents race conditions and guarantees data consistency.

## How to use the project
1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install the necessary packages.
4. Run `react-native run-android` or `react-native run-ios` to start the application.