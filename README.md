# PlunderTube Appcast Feed

This repository hosts the **public** Sparkle update feed for PlunderTube.

## Architecture

- **This repo (pt-appcast)**: Public appcast XML files that Sparkle checks for updates
- **pt-releases repo**: Private repository with actual release binaries (DMG/PKG files)
- **Authentication**: The PlunderTube app has an embedded GitHub PAT to download from the private pt-releases repo

## Update Channels

- **Stable**: https://raw.githubusercontent.com/danielraffel/pt-appcast/main/appcast.xml
- **Beta**: https://raw.githubusercontent.com/danielraffel/pt-appcast/main/appcast-beta.xml

## Version History

Starting fresh from v0.0.1 with conservative semantic versioning:
- **Patch** (0.0.X): Bug fixes, small improvements
- **Minor** (0.X.0): New features (requires explicit tagging or 3+ feature commits)
- **Major** (X.0.0): Breaking changes (requires explicit tagging)

## How It Works

1. PlunderTube checks this public repo for update information (no auth needed)
2. When an update is found, it uses the embedded GitHub PAT to download from private pt-releases repo
3. This allows us to keep the binaries private while the update feed is public