# download-policy

<p align="center">
  <a href="https://github.com/sebin-gg/download-policy/actions"><img src="https://github.com/sebin-gg/download-policy/actions/workflows/lint.yml/badge.svg" alt="Lint"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License"></a>
  <a href="https://github.com/sebin-gg/download-policy/stargazers"><img src="https://img.shields.io/github/stars/sebin-gg/download-policy?style=social" alt="Stars"></a>
  <a href="https://skills.sh/sebin-gg/download-policy"><img src="https://skills.sh/b/sebin-gg/download-policy" alt="skills.sh"></a>
</p>

> **Agents default to `curl` for everything; this makes them reach for
> aria2c first.** A small policy skill: multi-connection aria2c flags for
> direct downloads, package managers left on their own network stacks,
> curl/wget as fallback only.

## Highlights

- **aria2c first**: direct file downloads use aria2c's multi-connection
  mode when the source supports it:

  ```bash
  aria2c -x 16 -s 16 -k 1M --disk-cache=64M --stream-piece-selector=geom -c <URL>
  ```

- **Package managers untouched**: WinGet, npm, pnpm and friends keep their
  own supported network stacks — no downloader hijacking.
- **Honest fallback**: curl, wget, or native fetchers only when aria2c
  fails or isn't installed.

## Install

```bash
npx skills add sebin-gg/download-policy@download-policy
```

Restart your agent session after install so the skill loads.

## Use

Loads before any direct file download. Example prompts:

- "Download this ISO / tarball / dataset"
- "Fetch the release binary from this URL"

## Project layout

- `download-policy/SKILL.md` — the policy and the flag set.
- `CHANGELOG.md` — release notes per version.

## Requirements

- [`aria2`](https://aria2.github.io/) on PATH for the fast path; any of
  `curl`/`wget` as fallback.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

[MIT](LICENSE) © 2026 download-policy contributors
