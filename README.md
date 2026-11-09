# zone-core-repo

Core binary package repository for Zone Linux.

Served at: `https://zone-linux.github.io/zone-core-repo/x86_64/`

## Contents

Packages built from `zone-pkgbuild/core_pkgbuild/`:

| Package | Description |
|---|---|
| `zone-calamares-config` | Calamares 3.4 configuration, branding, polkit rule, launcher |
| `zone-grub-theme` | GRUB menu theme plus Zone `/etc/default/grub` and `40_custom` |
| `zone-release` | Pacman hooks and OS release files |

The old custom `grub` and `zone-calamares` packages were removed. Zone uses the
official `grub` package and the AUR `calamares` package instead.

## Updating

Build and publish from `zone-pkgbuild/`:

```bash
./build.sh --core --no-publish
./publish.sh --core --prune --verify
./publish.sh --core --commit        # commit locally; never pushes
```

`zone-grub-theme` no longer owns `/etc/default/grub` or `/etc/grub.d/40_custom`
because the `grub` package owns those paths. It stages the Zone versions under
`/usr/share/zone/grub/` and applies them from an install script and a pacman hook
that fires whenever `grub` is installed or upgraded.
