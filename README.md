# Simple Step Counter Spike using Google Fit API's

Android app which shows your latest step count, and your step count for the last week.

## Authors

Joost Funke Kupper

## Goals

The goal of this spike was to investigate the Google Fit integration into an Android app to collect step counter values and other health related values.

## Technologies used

- Android SDK
- Android Build Tools v23
- Android Support Repository
- Register a Google Project with an Android client per getting started instructions
  http://developers.google.com/fit/android/get-started

## Tasks undertaken
* https://developers.google.com/fit/android/get-api-key
* Create a new project on the Google API developer console, add credentials needed, and enabled Fitness API - https://console.developers.google.com
* Create new Android project and add necessary libraries to Gradle file.
* Used documentation and sample apps to create app which fetches step counts

## What was found out
The Fitness API's are available without the need of the user to have the Google Fit app installed 👍 There are various fields to collect the data, need to look into this more. Furthermore, data needs to be formatted and processed before being sent to the server.

There are two common forms of reading the data from Google Fit, through the `readDailyTotal()` and `readData()` functions.

There is a limited scope of data that is available 

https://developers.google.com/fit/android/data-types

Some data types require certain permissions to be turned on before enabling the data
https://developers.google.com/fit/android/authorization#scopes_for_google_fit_with_android_60_marshmallow

## Open issues /risks
The up to now step count is not the same as the aggregated step count, not sure why. Needs more investigation.
Also, you cannot rely that your data is the same as on the Google Fit app, as they perform other calculations in the app.

## Recommendations
Make sure that you subscribe your data recordings to made part of the Fitness History. Your app will perform the recording and uploading to the Fitness API.

## Getting up and running

1. Open project folder in Android Studio.
2. Perform a sync with Gradle to ensure dependencies are made available.
3. Add a new project via the Google Developer console - https://console.developers.google.com
4. Enable the Fitness API either via the 'Library' menu item or 'Enable APIs and services' button on the dashboard.
5. Add an 'OAuth Client ID' credentials as an Android Application Type.
6. Give the credentials the name of the project package `au.com.example.fitapispike`.
7. Use the provided keytool command line instructions to copy your debug SHA1 and paste in the field.
8. Provide the package name `au.com.example.fitapispike`, and hit 'Create'.
9. Select the OAuth consent screen tab, and provide a product name. Other fields can remain blank (except for email), and hit Save.
10. Run the application on a physical to test the step counter.
