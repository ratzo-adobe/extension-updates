# Ratzo extension update feed

This repository contains only the minimal public version metadata required by Ratzo extensions to detect updates.

It does **not** contain extension source code, installers, release notes, credentials, or authentication tokens. Every linked extension repository and release remains private. GitHub sign-in and explicit repository access are required to download an installer.

## Feed format

`updates.json` maps each extension key to its current version and direct private GitHub release asset URL.

When publishing a release:

1. Publish and verify the signed installer in the private extension repository.
2. Update its version and immutable release asset URL in `updates.json`.
3. Validate the JSON before pushing.

Clients reject non-HTTPS links and download URLs outside their configured GitHub repository.
