# Contributing

Thank you for your interest in contributing to the Hyphen OpenFeature providers! This repository holds every provider, one per directory:

| Directory | Language | Tooling | Package guide |
|---|---|---|---|
| `dotnet/` | .NET 8 | `dotnet` CLI | [dotnet/README.md](dotnet/README.md) |
| `go/` | Go | `go` toolchain | [go/CONTRIBUTING.md](go/CONTRIBUTING.md) |
| `java/` | Java | — (not implemented yet) | [java/README.md](java/README.md) |
| `javascript/server/` | TypeScript (Node.js) | npm | [javascript/server/CONTRIBUTING.md](javascript/server/CONTRIBUTING.md) |
| `javascript/web/` | TypeScript (browser) | npm | [javascript/web/CONTRIBUTING.md](javascript/web/CONTRIBUTING.md) |
| `python/` | Python | Poetry | [python/CONTRIBUTING.md](python/CONTRIBUTING.md) |

## Code of Conduct

Contributors are expected to maintain a respectful and inclusive environment for everyone involved in the project.

## Development

1. Fork and clone the repository.
2. `cd` into the directory of the provider you are changing. Every command in the package guides runs from that directory.
3. Make your change, then run that provider's tests and linters before you open a pull request.

Each provider is self-contained: there is no root-level build, and a change to one provider never needs changes to another.

## Commit messages

Commits and pull request titles **must** follow [Conventional Commits](https://www.conventionalcommits.org/). They drive versioning:

| Type | Effect on the package's version |
|---|---|
| `fix:` | patch (`1.2.3` → `1.2.4`) |
| `feat:` | minor (`1.2.3` → `1.3.0`) |
| `feat!:`, `fix!:` or a `BREAKING CHANGE:` footer | major (`1.2.3` → `2.0.0`) |
| `chore:`, `docs:`, `ci:`, `test:`, `refactor:`, `build:` | no release |

Use the provider as the scope, for example `fix(go): handle empty targeting key` or `feat(javascript-web): add cache TTL option`.

release-please decides which package a commit belongs to from the **files it changes**, not from the scope. Keep each pull request to one provider when you can: a `fix:` that touches two providers releases both.

## Continuous integration

Each provider has its own workflow in `.github/workflows/` (`<provider>-pr.yaml`). A workflow runs only when a pull request changes files in its provider's directory (or the workflow file itself), so a pull request usually shows checks for one provider.

## Releases

Releases are automated with [release-please](https://github.com/googleapis/release-please) (`release-please-config.json` and `.release-please-manifest.json` at the root):

1. After commits land on `main`, release-please opens a release pull request per provider, titled like `chore(main): release javascript-server 1.0.8`, which updates the version and `CHANGELOG.md`.
2. Merging that pull request tags the release (`go/vX.Y.Z`, `javascript-server-vX.Y.Z`, `javascript-web-vX.Y.Z`, `python-vX.Y.Z`), creates the GitHub release and publishes the package (npm, PyPI; Go is published by the tag itself).
3. The .NET provider is released manually with the `.NET Release` workflow (`dotnet-release.yaml`) after bumping `<Version>` in `dotnet/src/Hyphen.OpenFeature.Provider/OpenFeature.Provider.csproj`.

## Creating issues

- Search for existing issues first.
- Say which provider (language) and version the issue is about.
- Provide clear reproduction steps and the relevant environment details.

## Need help?

Feel free to ask questions by creating an issue or starting a discussion.

For detailed information about creating pull requests, see the [GitHub documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).
