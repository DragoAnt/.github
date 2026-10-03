# Contributing to DragoAnt

Thank you for helping. This guide applies to every DragoAnt repository that does not ship its own `CONTRIBUTING.md`; a repository's own guide wins where the two differ.

## Before you start

- **Small fixes** (typos, docs, an obvious bug) — open a pull request directly.
- **Anything larger** — open an issue first so the approach can be agreed before you write the code.
- **Security issues** — report them privately, see [SECURITY.md](./SECURITY.md).

## Build and test

Most repositories import shared MSBuild files from a git submodule, so clone with submodules:

```sh
git clone --recurse-submodules https://github.com/DragoAnt/<repository>.git
```

Install the .NET SDK pinned in the repository's `global.json`, plus the runtimes of every target framework the projects list, then run the same steps as CI from the repository root:

```sh
dotnet restore
dotnet build -c Release --no-restore
dotnet test -c Release --no-build
```

## Pull requests

- Branch from the default branch and target it.
- Add or update tests for every behavior change, and a regression test for every bug fix.
- Keep the build warning-free.
- Update the README (and the package README, if the repository has one) when usage changes.
- Keep a pull request to one topic; unrelated clean-ups go in their own pull request.
- The `ci` workflow must pass.

## Releases

Maintainers publish packages to nuget.org by creating a GitHub release whose tag is the package version (`v1.2.3` or `v1.2.3-beta.1`).

## Code of conduct

Everyone taking part follows the [Code of Conduct](./CODE_OF_CONDUCT.md).
