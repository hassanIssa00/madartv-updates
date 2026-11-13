# Madar TV public Android releases

This public repository contains only update metadata, checksums via GitHub Release asset digests, and APK release binaries. Application source code remains in the private source repository.

Users can download the current APK from the **Releases** page. Current Android app builds query GitHub's public latest-release API, then download the matching release APK. Older builds use `latest.json` as a compatibility feed.

The app checks the APK's SHA-256, package name, version code, and installed signing certificate before opening Android's standard install confirmation.

## Publish a release

From the private app checkout, build a higher Android `versionCode` and run `MadarFlutter/scripts/publish_public_update.ps1`. The script verifies the APK package/version/signature, creates or updates the release asset, then publishes `latest.json` for older app builds.

Only publish APKs produced from the private app project and signed with the same release certificate as the installed app. Do not upload source code, signing keys, credentials, or `.env` files here.
