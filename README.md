# @ecssc/commitlint-config

Shared commitlint configuration for ECSSC projects. Enforces the [Conventional Commits](https://www.conventionalcommits.org) format and ignores automated `release:` commits. Requires @commitlint/cli 20+.

## Installation

These packages are published to GitHub Packages. Add an `.npmrc` to your project pointing the `@ecssc` scope at that registry:

```
@ecssc:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${NODE_AUTH_TOKEN}
```

GitHub Packages requires authentication even for public packages, so `NODE_AUTH_TOKEN` must hold a token with the `read:packages` scope. Then install:

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

Each commit message must start with one of these types:

| Type | Description |
|------|-------------|
| `feat:` | New feature |
| `fix:` | Bug fix |
| `perf:` | Performance improvement |
| `refactor:` | Code restructuring |
| `docs:` | Documentation |
| `style:` | Formatting |
| `test:` | Tests |
| `build:` | Build system |
| `ci:` | CI configuration |
| `chore:` | Maintenance |

Mark a breaking change with a `!` suffix (e.g. `feat!:`) or a `BREAKING CHANGE:` footer.

commitlint only checks this format. Version bumps and changelog grouping are applied by the release tooling (see [`@ecssc/release-it-config`](https://github.com/ecssc/release-it-config)) — typically `feat` for a minor release, `fix` and `perf` for a patch, and a breaking change for a major.
