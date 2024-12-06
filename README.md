# Expo Linking API Silent Authentication Failure

This repository demonstrates a bug in Expo's `Linking` API where authentication failures when opening URLs are handled silently, providing no feedback to the user or the application.

## Bug Description

When using `Linking.openURL` to open a URL that requires authentication (e.g., a login page), the function may succeed even if the authentication process fails.  There is no mechanism within the API to determine if the authentication was successful or if the user canceled the login.

## Reproduction

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the application.
4. Observe the lack of error handling when authentication fails.

## Solution

The solution involves using a custom webview to handle the authentication process and to relay success/failure information back to the application.