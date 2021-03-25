# AppCode Experiment

This project exists to make sense of some [AppCode](https://www.jetbrains.com/objc/) errors which occur when an Xcode project exists in a folder which contains a `build.gradle` file but that `build.gradle` is a module-level `build.gradle` file and not a root-level `build.gradle` file.

The trick to get it all to work is to follow these steps:

1. Open the Xcode project in AppCode.
2. Tap the 'Load Gradle Project' button in the 'Gradle build scripts found' popup.
3. Observe the `"Task 'wrapper' not found in project ':iOS'."` error message in the Build window.
4. Navigate to AppCode's Gradle settings (you can get there via AppCode preferences or via the Gradle window).
5. Observe the `"'gradle-wrapper.properties' not found"` error message.
6. Change the 'Use Gradle from' setting to 'Specified location'.
7. Specify the location of Gradle on your machine if AppCode hasn't located it automatically (for me AppCode detects it at `/usr/local/Cellar/gradle/6.8.3/libexec`).
7. Apply changes.
8. Observe that the build now succeeds.