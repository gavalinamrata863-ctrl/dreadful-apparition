# DueMate – Android Assignment Tracker

A beginner-friendly native Android project built with Kotlin and Jetpack Compose.

## Included features
- Add, edit and delete assignments
- Assignment name, subject, assigned date, due date and last submission date
- Pending, completed and overdue status
- High / Medium / Low priority
- Dashboard counts and search/filter
- Local offline persistence
- One-day-before and due-day reminders at 9:00 AM
- Daily pending-assignment reminder

## Date rules
Enter dates in `YYYY-MM-DD` format.
The app treats the **last submission date** as the final deadline for overdue status and deadline notifications. The due date is displayed separately.

## Build APK using GitHub from an Android phone

1. Download and extract `DueMate-Android-Project.zip` on your phone.
2. Open Chrome and sign in to GitHub.
3. Create a new public or private repository named `DueMate`.
4. Choose **Add file → Upload files**.
5. Upload the contents of the extracted `DueMate` folder (not the ZIP itself). Make sure `.github/workflows/build-apk.yml` is included. If GitHub's mobile page hides dot-folders, switch Chrome to **Desktop site**.
6. Commit the files to the `main` branch.
7. Open the repository's **Actions** tab.
8. Select **Build DueMate APK** and press **Run workflow**. A push to `main` also starts a build automatically.
9. Wait for the workflow to finish with a green check.
10. Open the completed workflow run. Under **Artifacts**, tap `DueMate-debug-APK` to download the APK ZIP.
11. Extract that downloaded artifact ZIP. It contains `app-debug.apk`.
12. Tap `app-debug.apk` to install. Android may ask you to allow Chrome or Files to install unknown apps. Only allow this for the APK you built from your own repository.

## Important notes
- Notifications require notification permission on Android 13 and newer.
- Android battery optimization may delay background reminders. WorkManager is designed for reliable deferrable background work, not exact-to-the-minute alarms.
- The daily reminder runs approximately once every 24 hours; Android may defer it.
- The app currently stores data locally on each phone. Sharing the APK shares the app, **not** assignment data between classmates.
- This is a debug APK for project testing. A release APK for public distribution should be signed with a private signing key.
- The project uses Android Gradle Plugin 8.7.3, Gradle 8.9 and JDK 17.
