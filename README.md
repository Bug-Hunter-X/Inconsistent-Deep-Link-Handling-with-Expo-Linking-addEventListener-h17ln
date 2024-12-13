# Inconsistent Deep Link Handling with Expo Linking.addEventListener

This repository demonstrates a bug where Expo's `Linking.addEventListener` does not consistently trigger deep link events.  The issue is particularly noticeable when the app is in the background or has been completely closed and reopened.

## Bug Description

The `Linking.addEventListener` function, intended to listen for deep link URLs, fails to reliably invoke its callback.  This makes it impossible for the application to correctly handle deep links in these scenarios.

## Reproduction Steps

1. Clone this repository.
2. Run the app in Expo Go or a simulator.
3. Send a deep link to the application (e.g., through a browser or another app).
4. Observe that the event listener may not always trigger the callback, especially when the app is in the background or closed.

## Solution

The provided `bugSolution.js` file offers a workaround that improves the reliability of deep link handling. This may involve using `Linking.getInitialURLAsync` to check for a deep link on app launch.