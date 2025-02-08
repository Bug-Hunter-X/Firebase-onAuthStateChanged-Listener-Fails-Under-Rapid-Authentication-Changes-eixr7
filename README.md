# Firebase onAuthStateChanged Listener Inconsistency

This repository demonstrates a subtle bug related to Firebase's `onAuthStateChanged` listener.  Under conditions of rapid authentication state changes (e.g., repeated login/logout attempts, network instability), the listener might miss updates or become unreliable.  This is often difficult to reproduce consistently but can lead to significant issues in application behavior.  The included `authBug.js` shows how the problem can manifest.  The `authBugSolution.js` offers a solution to improve the robustness of the listener.

## Problem Description

The core problem lies in the potential for the `onAuthStateChanged` listener to get overwhelmed when authentication status transitions occur very quickly.  This is particularly relevant in applications with features that involve frequent user sign-in/sign-out actions or may experience intermittent network connectivity.