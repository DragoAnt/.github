# Contributing to DragoAnt

Thank you for helping. This guide applies to every DragoAnt repository that does not ship its own `CONTRIBUTING.md`; a repository's own guide wins where the two differ.

## Before you start

- **Small fixes** (typos, docs, an obvious bug) — open a pull request directly.
- **Anything larger** — open an issue first so the approach can be agreed before you write the code.
- **Security issues** — report them privately, see [SECURITY.md](./SECURITY.md).

## Build and test

The shared build settings come from [MSBuildKit](https://github.com/DragoAnt/MSBuildKit), committed as plain files under `.toolkit/`, so a plain clone builds — no submodules, nothing restored from a private feed:

```sh
git clone https://github.com/DragoAnt/<repository>.git
```

Install the .NET SDK pinned in the repository's `global.json`, plus the runtimes of every target framework the projects list. `global.json` also selects Microsoft.Testing.Platform v2 as the test runner, so `dotnet test` takes the `.slnx` solution with `--solution`. From the repository root, run the same steps as CI:

```sh
dotnet restore
dotnet build -c Release --no-restore
dotnet test --solution <Name>.slnx -c Release --no-build
```

Tests are xUnit v3 projects named `*.Tests`; the kit wires the test platform, coverage and reports into them. CI runs these steps through the shared [`dotnet-build.yml`](https://github.com/DragoAnt/.github/blob/main/.github/workflows/dotnet-build.yml) workflow, which also gates on coverage where the repository sets a threshold.

### The build kit

Don't edit `.toolkit/` by hand. Move to another kit release with its update script and commit the result in its own pull request:

```sh
sh .toolkit/update.sh --version <x.y.z>     # or: pwsh .toolkit/update.ps1 -Version <x.y.z>
```

Repository settings live next to it: `Directory.Build.props` (target frameworks, copyright), `Directory.Version.props` (the next release's `VersionPrefix`) and `Directory.Packages.props` (package versions).

A repository that still has a `.sln` and no `.toolkit/` builds with the same three commands against its solution file; follow its own README where it differs.

## Pull requests

- Branch from the default branch and target it.
- Add or update tests for every behavior change, and a regression test for every bug fix.
- Keep the build warning-free.
- Update the README (and the package README, if the repository has one) when usage changes.
- Keep a pull request to one topic; unrelated clean-ups go in their own pull request.
- The `ci` workflow must pass.

## Releases

Maintainers publish packages to nuget.org by creating a GitHub release whose tag is the package version (`v1.2.3` or `v1.2.3-beta.1`); the kit takes the version from the tag. Never push packages by hand.

## Code of conduct

Everyone taking part follows the [Code of Conduct](./CODE_OF_CONDUCT.md).
