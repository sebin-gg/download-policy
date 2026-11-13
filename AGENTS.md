# AGENTS.md — download-policy

Behavioral rules for AI agents working in this repository.

## Rules

- **Conventional Commits only:** `feat|fix|perf|docs|test|refactor|ci|chore|revert(scope):`.
- **Green CI before anything lands:** `lint.yml` (skills-ref validation + frontmatter lint) must pass before merge or push to `main`.
- **Version + changelog move together:** bump `metadata.version` in `download-policy/SKILL.md` frontmatter and add a matching `CHANGELOG.md` entry in the same commit.
- **Docs move together:** `README.md`, `SKILL.md`, and `CHANGELOG.md` are updated in the same commit when behavior changes.
- **Branch hygiene:** delete branches after they merge (local + remote). This repo's own AGENTS rules follow the branch-hygiene skill.
- Never commit `.env`, tokens, or generated artifacts.

## Verify (run before you commit)

```powershell
pip install skills-ref
agentskills validate download-policy
```
