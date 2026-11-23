# Regis APK versions

APK archive of Regis Android builds. This repository contains APK artifacts and checksums only; the
source code and server configuration live in a separate private repository.

## Latest

| Version | File | Date | Notes |
| --- | --- | --- | --- |
| 0.3.0 (versionCode 3) | `apk/regis-0.3.0-release.apk` | 2026-11-24 | Release-signed; new-chat subject greeting; daily plan server-side; consent v3; feedback; parent PIN fix; production API |
| 0.1.1 (versionCode 2) | `apk/regis-0.1.1-pin-fix-debug.apk` | 2026-11-23 | Debug-signed; parent PIN persists after restart; feedback button; production API |
| 0.1.0 (versionCode 1) | `apk/regis-0.1.0-feedback-debug.apk` | 2026-11-23 | Debug-signed; consent v3; child feedback button; production API URL |

SHA-256:

```text
026cce3a6c45c7711d006df7986835f35465292405a3b1046a5e492a20165c55  apk/regis-0.3.0-release.apk
d92ab069ff68f3c54169134273c7c9007e4a10d57931101806050470e38d357b  apk/regis-0.1.1-pin-fix-debug.apk
9b3d0d51367aced9a2fe707ade582ddfc31e4820601463161cb6385056fe3a1e  apk/regis-0.1.0-feedback-debug.apk
```

**0.3.0 is release-signed.** It cannot install over the debug-signed 0.1.x builds: uninstall the old
app first. Server history survives; the local cache and the token on the phone do not, so keep the
token safe. Future 0.3.x builds with the same release key install as updates.

0.1.1 installs over 0.1.0 because both are debug-signed with the same certificate and `versionCode` is
higher. Keep the token and PIN; the update does not clear app data.

## Install

- Android 8.0 or newer (`minSdk 26`).
- Transfer the APK to the phone and open it; allow installation from this source if prompted.
- The child token and the parent token are issued in the admin page and are not stored in this
  repository.
- The **Обратная связь** action is in the chat overflow menu.

## Signing

- 0.3.0 and later: release-signed with the owner's key. Future builds with the same key update in
  place; losing the key means no future updates.
- 0.1.0 and 0.1.1: historical debug-signed builds. A release-signed APK cannot update over them.
- Never commit the keystore, `keystore.properties`, or passwords.

## Rules

- Do not commit tokens, passwords, `.dev.vars`, message content, photos, or textbook files here.
- The repository is currently public on GitHub. APKs contain no tokens, but treat APK links as public;
  share them only with the family.
- Keep one APK per version and update the table and checksum together.
