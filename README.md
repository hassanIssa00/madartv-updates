# Madar TV public Android releases

This repository contains only the public Android update manifest and release notes. Application source code remains in the private source repository.

Users can download the current APK from the **Releases** page. The Android app reads `latest.json`, downloads the matching APK, checks its SHA-256 and installed signing certificate, then opens Android's standard install confirmation.

## Publish a release

From the private app checkout, build a higher Android `versionCode` and use `MadarFlutter/scripts/publish_public_update.ps1`. The script verifies the APK package/version/signature, creates or updates the release asset, then publishes `latest.json`.

Only publish release APKs produced from the private app project and signed with the same release certificate as the installed app. Do not upload source code, signing keys, credentials, or `.env` files here.
