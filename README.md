# ScreenMate AI Updates

Public distribution channel for signed ScreenMate AI Windows releases.

This repository must **not** contain private source code, API credentials, PATs, or signing private keys.

## Release layout

- `stable/latest.json`: signed update manifest.
- `stable/ScreenMateAI-Setup-x.y.z.exe`: installer asset attached to a GitHub Release.
- GitHub Releases are the download origin.

## Client verification

The client must:
1. Fetch the manifest over HTTPS.
2. Verify the Ed25519 signature against the public key embedded in the application.
3. Validate the version and HTTPS asset URL allowlisted to this repository.
4. Download to a temporary directory.
5. Verify exact SHA-256 and byte length.
6. Launch the installer only after all checks pass.
7. Never run arbitrary scripts or accept an unsigned manifest.

No release is published until the signing private key and Windows code-signing strategy are provisioned.
