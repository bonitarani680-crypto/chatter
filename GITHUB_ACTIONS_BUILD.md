# Build the Android APK on GitHub

## Upload the project

1. Create a new repository on GitHub, for example `chatter`.
2. Upload the contents of this project to the repository root. The `.github/workflows/build-apk.yml` file must be present at exactly that path.
3. Commit the files to the `main` branch.

You can upload the ZIP from the GitHub mobile app or from GitHub in a mobile browser. If GitHub uploads the ZIP as one file instead of project contents, extract it first and upload the contents of the `chatter` folder.

## Start a build manually

1. Open the repository on GitHub.
2. Tap **Actions**.
3. Select **Build Android APK**.
4. Tap **Run workflow**, select the `main` branch, and tap **Run workflow** again.
5. Wait until the workflow has a green check mark.
6. Open the completed workflow run, scroll to **Artifacts**, and download `chatter-release-apks`.
7. Extract the downloaded artifact ZIP. It contains release APKs for supported CPU architectures.

The workflow also runs automatically whenever a commit is pushed to `main` or `master`.

## If the build fails

Open the failed workflow run and copy the error from the failed step. The most useful steps to share are **Install Dart dependencies** and **Build release APKs**.

The workflow removes the archived `android/local.properties` file because it contains machine-specific paths. GitHub Actions creates the correct Android/Flutter paths on its runner.
