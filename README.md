# DragoAnt/.github

Organization defaults for every DragoAnt repository.

| Path | What it does |
| --- | --- |
| [profile/README.md](./profile/README.md) | The organization's front page on GitHub. |
| [CONTRIBUTING.md](./CONTRIBUTING.md), [SECURITY.md](./SECURITY.md), [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md), [SUPPORT.md](./SUPPORT.md) | Default community health files, shown in any repository that has none of its own. |
| [.github/ISSUE_TEMPLATE](./.github/ISSUE_TEMPLATE), [.github/pull_request_template.md](./.github/pull_request_template.md) | Default issue forms and pull request template. |
| [.github/workflows/dotnet-build.yml](./.github/workflows/dotnet-build.yml) | Reusable workflow: restore, build, test, coverage, pack. |
| [workflow-templates](./workflow-templates) | `ci` and `release` starters on each repository's **Actions → New workflow** page. |

## Reusable workflow `dotnet-build.yml`

Restores, builds and tests a .NET solution on Microsoft.Testing.Platform, writes a test table and a coverage summary to the job summary, and uploads the `test-results`, `coverage` and (with `pack: true`) `packages` artifacts. It needs only `contents: read`.

```yaml
jobs:
  build:
    uses: DragoAnt/.github/.github/workflows/dotnet-build.yml@<full-commit-sha> # main
    with:
      version: 0.0.0-ci.${{ github.run_number }}
      coverage-threshold: 70
```

| Input | Default | Meaning |
| --- | --- | --- |
| `solution` | single `*.slnx`, else `*.sln`, at the root | Solution or project to build. |
| `dotnet-version` | `8.0.x` and `9.0.x` | Extra SDKs, one per line, on top of the SDK pinned in `global.json`. |
| `global-json-file` | `global.json` | Ignored when absent. |
| `configuration` | `Release` | Build configuration. |
| `version` | empty | Passed as `-p:Version`; empty leaves versioning to the repository. |
| `test-arguments` | xUnit v3 TRX + JUnit reports, Cobertura coverage | Extra `dotnet test` arguments. JUnit files feed the test table. |
| `coverage-threshold` | `0` | Minimum merged line coverage in percent; `0` only reports. |
| `coverage-assembly-filters` | `-*.Tests;-*.Tests.*;-*.Benchmarks` | ReportGenerator assembly filters. |
| `pack` | `false` | Pack and upload the `packages` artifact. |
| `runs-on` | `ubuntu-24.04` | Runner label. |
| `timeout-minutes` | `30` | Job timeout. |

Pin the reference to a full commit SHA in each caller; Dependabot's `github-actions` updates keep it current. The workflow templates reference `@main` so a new repository starts from the latest version — pin it after adding.

## Publishing to nuget.org

The `release` template publishes when a GitHub release is published. One-time setup per repository:

1. **Settings → Environments → New environment** `nuget`, with yourself as required reviewer and a `v*` tag deployment rule.
2. **nuget.org → Trusted Publishing → Add policy**: owner `DragoAnt`, the repository, workflow file `release.yml`, environment `nuget`.
3. Optional: a repository variable `NUGET_USER` when the nuget.org account that owns the policy is not `DragoAnt`.

Then create a release whose tag is the version: `v1.2.3`, or `v1.2.3-beta.1` with **Set as a pre-release** ticked.

## License

[MIT](./LICENSE)
