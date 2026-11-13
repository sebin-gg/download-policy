---
name: download-policy
description: Use before direct file downloads. Prefer aria2c with high-speed multi-connection flags; use curl/wget only if aria2c fails or is unavailable.
license: MIT
allowed-tools: Bash
metadata:
  version: "1.0.0"
  tags: "download,aria2c,curl,wget"
---

# Download Policy

- Use aria2c for direct file downloads when the source supports it.
- For maximum download speed with aria2c, use these flags when suitable:

    aria2c -x 16 -s 16 -k 1M --disk-cache=64M --stream-piece-selector=geom -c <URL>

- Package managers such as WinGet, npm, and pnpm use their own supported network stacks. Use their documented network settings unless they expose an external downloader adapter.
- Fall back to standard tools (curl, wget, or native fetchers) if aria2c fails or is unavailable.
