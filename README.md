# Regis APK versions

Private archive of Regis Android builds. This repository contains APK artifacts and checksums only;
the source code and server configuration live in a separate private repository.

## Latest

| Version | File | Date | Notes |
| --- | --- | --- | --- |
| 0.1.0 (versionCode 1) | `apk/regis-0.1.0-feedback-debug.apk` | 2026-11-23 | Consent v3, child feedback button, production API URL |

SHA-256:

```text
9b3d0d51367aced9a2fe707ade582ddfc31e4820601463161cb6385056fe3a1e  apk/regis-0.1.0-feedback-debug.apk
```

## Install

- Android 8.0 or newer (`minSdk 26`).
- Transfer the APK to the phone and open it; allow installation from this source if prompted.
- The child token and the parent token are issued in the admin page and are not stored in this
  repository.
- The **Обратная связь** action is in the chat overflow menu.

## Signing

This is a **debug-signed** build with the standard Android debug certificate. A future release-signed
APK cannot update over it: uninstall the debug build first, then install the release build. Server
history survives; the local cache and the token on the phone do not, so keep the token safe.

## Rules

- Do not commit tokens, passwords, `.dev.vars`, message content, photos, or textbook files here.
- Keep one APK per version and update the table and checksum together.
- APKs are private family artifacts; do not publish this repository.
