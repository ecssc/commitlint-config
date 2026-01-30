# @ecssc/commitlint-config

Shared commitlint configuration for ECSSC projects. Enforces conventional commit format.

## Installation

```bash
npm install --save-dev @ecssc/commitlint-config @commitlint/cli
```

## Usage

Create a `commitlint.config.mjs`:

```javascript
export default {
  extends: ['@ecssc/commitlint-config'],
}
```

## Commit Format

Commits must follow the conventional commits specification:

| Type | Description | Version Bump |
|------|-------------|--------------|
| `feat:` | New feature | Minor |
| `fix:` | Bug fix | Patch |
| `docs:` | Documentation | None |
| `style:` | Formatting | None |
| `refactor:` | Code restructuring | None |
| `perf:` | Performance improvement | Patch |
| `test:` | Tests | None |
| `build:` | Build system | None |
| `ci:` | CI configuration | None |
| `chore:` | Maintenance | None |

Breaking changes use `!` suffix (e.g., `feat!:`) or `BREAKING CHANGE:` in the body, triggering a major version bump.