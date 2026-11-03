# Hyphen OpenFeature Providers

[OpenFeature](https://openfeature.dev) providers for Hyphen Toggle, all in one repository.
Each provider sits in its own directory with its own build, tests and release cycle. The published package names are the same as before the providers moved here.

## Providers

| Language | Directory | Package | Install |
|---|---|---|---|
| .NET | [`dotnet/`](dotnet) | `Hyphen.OpenFeature.Provider` (NuGet) | `dotnet add package Hyphen.OpenFeature.Provider` |
| Go | [`go/`](go) | [`github.com/hyphen/open-feature/go`](https://pkg.go.dev/github.com/hyphen/open-feature/go) | `go get github.com/hyphen/open-feature/go` |
| JavaScript (server) | [`javascript/server/`](javascript/server) | [![npm](https://img.shields.io/npm/v/@hyphen/openfeature-server-provider)](https://www.npmjs.com/package/@hyphen/openfeature-server-provider) | `npm install @hyphen/openfeature-server-provider` |
| JavaScript (web) | [`javascript/web/`](javascript/web) | [![npm](https://img.shields.io/npm/v/@hyphen/openfeature-web-provider)](https://www.npmjs.com/package/@hyphen/openfeature-web-provider) | `npm install @hyphen/openfeature-web-provider` |
| Python | [`python/`](python) | [![PyPI](https://img.shields.io/pypi/v/hyphen-openfeature-provider)](https://pypi.org/project/hyphen-openfeature-provider/) | `pip install hyphen-openfeature-provider` |
| Java | [`java/`](java) | Planned | — |

See each directory's README for setup, configuration and usage.

## Where the providers came from

The providers used to live in separate repositories. They were moved here with their full commit history:

| Previous repository | New location |
|---|---|
| [Hyphen/openfeature-provider-dotnet](https://github.com/Hyphen/openfeature-provider-dotnet) | [`dotnet/`](dotnet) |
| [Hyphen/openfeature-provider-go](https://github.com/Hyphen/openfeature-provider-go) | [`go/`](go) |
| [Hyphen/openfeature-provider-java](https://github.com/Hyphen/openfeature-provider-java) | [`java/`](java) |
| [Hyphen/openfeature-provider-javascript-server](https://github.com/Hyphen/openfeature-provider-javascript-server) | [`javascript/server/`](javascript/server) |
| [Hyphen/openfeature-provider-javascript-web](https://github.com/Hyphen/openfeature-provider-javascript-web) | [`javascript/web/`](javascript/web) |
| [Hyphen/openfeature-provider-python](https://github.com/Hyphen/openfeature-provider-python) | [`python/`](python) |

> **Go users:** the module path changed from `github.com/hyphen/openfeature-provider-go` to `github.com/hyphen/open-feature/go`. Update your imports (for example `github.com/hyphen/open-feature/go/pkg/toggle`) when you upgrade.

## Releases

Releases are managed by [release-please](https://github.com/googleapis/release-please) from the repository root, and each package is versioned on its own:

1. Changes land on `main` as [Conventional Commits](https://www.conventionalcommits.org/).
2. release-please opens or updates a release pull request for every package that has releasable changes.
3. Merging a release pull request tags the release, creates the GitHub release and publishes the package.

| Package | Tag format | Published by |
|---|---|---|
| Go | `go/vX.Y.Z` | the tag itself (Go module proxy) |
| JavaScript (server) | `javascript-server-vX.Y.Z` | `release.yaml` → npm |
| JavaScript (web) | `javascript-web-vX.Y.Z` | `release.yaml` → npm |
| Python | `python-vX.Y.Z` | `release.yaml` → PyPI |
| .NET | — | `dotnet-release.yaml` (manual dispatch) → NuGet |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
