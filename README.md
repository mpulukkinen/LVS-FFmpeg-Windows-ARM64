# LVS FFmpeg Windows ARM64

Reproducible Windows ARM64 FFmpeg builds used by Lyric Video Studio.

This repository builds a pinned FFmpeg/vcpkg configuration for **Windows ARM64 only** and publishes versioned release ZIPs for use by Lyric Video Studio's local and CI builds.

## Current build

- FFmpeg: **9.0.2**
- Target: **Windows ARM64** (`arm64-windows`)
- Release revision: **lvs1**
- vcpkg baseline: `18ff00a7d2697e23f22e2a2293c3fa6468a50c06`
- FFmpeg feature policy: vcpkg `ffmpeg[all,ffmpeg,ffprobe]`
- Includes OpenH264 (`libopenh264`)
- Includes AV1 support from the LGPL-compatible vcpkg feature set (libaom, dav1d and SVT-AV1 where supported)
- Does **not** enable FFmpeg `gpl` or `nonfree`, x264, x265 or fdk-aac

## Release asset

`ffmpeg-9.0.2-windows-arm64-lgpl-lvs1.zip`

The ZIP contains `ffmpeg.exe`, `ffprobe.exe`, FFmpeg shared libraries, required runtime dependency DLLs and collected vcpkg copyright/license notices.

## Updating

Do not track `latest`. Update the pinned vcpkg commit/FFmpeg version deliberately, test the resulting binaries on real Windows ARM64 hardware and then bump the LVS release revision (`lvs1`, `lvs2`, ...).

The release workflow runs only when the build manifest/workflow changes or when started manually. Re-running the same revision replaces the release asset rather than silently changing the version used by Lyric Video Studio.

This repository contains build scripts only. FFmpeg and its dependencies retain their respective upstream licenses; license notices are bundled into each release archive.
