# ScreenMate AI Updates

Public distribution channel for signed ScreenMate AI Windows releases.

## Security status

The repository is prepared, but **no production update is published yet**.

Do not add installers manually until the application updater is integrated, the Ed25519 public key is pinned in the client, and the release signing secret is configured.

## Planned release layout

- `stable/latest.json`: Ed25519-signed canonical manifest.
- GitHub Release asset: Windows installer.
- Manifest contains product, channel, SemVer version, publication time, asset URL, size, SHA-256, minimum supported version, and release notes.

## Client must verify

1. HTTPS origin is exactly this repository's GitHub Releases / raw manifest endpoint.
2. Ed25519 signature using the public key embedded in the app.
3. Product and channel match the installed app.
4. Version is strictly newer (unless user explicitly chooses repair/reinstall).
5. Asset host/path is allowlisted to this repository.
6. Download size and SHA-256 match the signed manifest.
7. Only after verification, launch installer with user consent.
8. Keep rollback option until updated app completes first launch.

A hash without a signature is not sufficient. A public manifest is untrusted until signature verification succeeds.
