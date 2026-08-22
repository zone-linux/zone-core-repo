# zone-core-repo

Core binary package repository for Zone Linux.

Served at: `https://zone-linux.github.io/zone-core-repo/x86_64/`

## Contents

Packages built from `zone-pkgbuild/core_pkgbuild/`:

| Package | Description |
|---|---|
| `grub` | Custom GRUB build with Zone patches (requires update from 2.06 to current) |
| `zone-calamares` | Calamares installer (updated to 3.3.x — rebuild required on Linux host) |
| `zone-calamares-config` | Calamares configuration for Zone |
| `zone-grub-theme` | GRUB menu theme |
| `zone-release` | Pacman hooks and OS release files |

## Updating

After building packages on a Linux host, run `zone-pkgbuild/upd-core.sh` to add the
new `.pkg.tar.zst` files and regenerate the pacman repo database.

## Note

The `grub` package in this repo is at version 2.06-4. The PKGBUILD must be updated
on a Linux build host (pinned git commits need updating to current upstream HEAD).
The `zone-calamares` package has been updated to 3.3.x in the PKGBUILD but the binary
repo still contains 3.2.53-1 — a rebuild is required.
