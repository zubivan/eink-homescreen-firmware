# eink-homescreen firmware releases

Signed firmware images for the eink-homescreen display. This repository only
hosts **release assets**: each release contains

- `eink-homescreen-X.Y.Z.bin`: the ESP32-S3 application image
- `manifest.json`: version, image URL, size, SHA-256
- `manifest.json.sig`: Ed25519 signature over the manifest

Devices fetch `releases/latest/download/manifest.json` (and `.sig`), verify the
signature with the public key built into their firmware, check the image hash
while downloading, and only then install. Anything not signed with the project
key is rejected, so the contents of this repository are not trusted by
themselves.

The source lives in a private repository. No credentials are involved in
fetching updates.
