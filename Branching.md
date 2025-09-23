# Branching Strategy — DDDS

## Permanent branches
- `main` → Always stable/playable. Used for tagged builds/releases.
- `develop` → Integration branch for the next version. Features merge here first.

## Temporary branches
- `feature/<slug>` → New work or experiments off `develop`.
  - Examples:
    - `feature/drone-link`
    - `feature/bio-matter-pickup`
    - `feature/package-drop-system`
    - `feature/employee-obituary`
- `hotfix/<slug>` → Emergency fixes off `main` (then merge back to `main` + `develop`).
- `release/<tag>` (optional) → Stabilization before a big demo (only bugfixes).

## Naming rules
- Use lowercase + hyphens.
- Keep it short and specific: `feature/<area>-<what>`.

## Flow
1) `git switch -c feature/<slug> develop`
2) Commit work → push → open PR into `develop`
3) Test on `develop`
4) Merge `develop` → `main` when stable for a build
5) Tag a release: `v0.62`, `demo-v0.1`, etc.

## Commit messages (keep it clear)
- Imperative mood, short summary:
  - `Add drone-employee reconnect timer`
  - `Fix package drop respawn bug`
  - `Tune obituary camera framing`
- If multiple changes, add a short body list.

## Tags / Releases
- Use semantic-ish tags:
  - Pre-alpha demos: `demo-v0.1`, `demo-v0.2`
  - Internal builds: `v0.62-internal`
  - Public releases: `v0.62`

> Employees are disposable. Branches are not.
