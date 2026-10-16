# Ratzo extension update feed

This repository contains only the minimal public version metadata required by Ratzo extensions to detect updates.

It does **not** contain extension source code, installers, release notes, credentials, or authentication tokens. Every linked extension repository and release remains private.

Current extension clients use this feed to detect new versions, but their **Download** action opens `https://www.ratzo.net/projects`. Private GitHub asset URLs remain in the feed for validation and compatibility with older installed clients.

## Feed format

`updates.json` maps each extension key to its current version and direct private GitHub release asset URL. The asset URL is updater metadata, not the current friend-facing download destination.

When publishing a release:

1. Publish and verify the signed installer in the private extension repository.
2. Update its version and immutable release asset URL in `updates.json`.
3. Validate the JSON before pushing.

Clients reject non-HTTPS links and asset URLs outside their configured GitHub repository. Current clients refresh once on every panel launch and every six hours while the panel remains open.
