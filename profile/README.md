# DragoAnt

Small, focused .NET libraries for System.Text.Json, Entity Framework Core and dependency injection — MIT-licensed and published on [nuget.org](https://www.nuget.org/profiles/DragoAnt).

## Packages

| Repository | What it is | NuGet |
| --- | --- | --- |
| [Extensions.System.Text.Json](https://github.com/DragoAnt/Extensions.System.Text.Json) | Mask or extract JSON values by property-path rules in one streaming pass | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.System.Text.Json.Observer?label=DragoAnt.System.Text.Json.Observer)](https://www.nuget.org/packages/DragoAnt.System.Text.Json.Observer) |
| [Extensions.EntityFrameworkCore](https://github.com/DragoAnt/Extensions.EntityFrameworkCore) | Conventions, static and historical migrations, entity definitions for EF Core | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.EntityFrameworkCore?label=DragoAnt.EntityFrameworkCore)](https://www.nuget.org/packages/DragoAnt.EntityFrameworkCore) |
| [Extensions.DependencyInjection](https://github.com/DragoAnt/Extensions.DependencyInjection) | Extensions for `Microsoft.Extensions.DependencyInjection` | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Extensions.DependencyInjection?label=DragoAnt.Extensions.DependencyInjection)](https://www.nuget.org/packages/DragoAnt.Extensions.DependencyInjection) |
| [Shared](https://github.com/DragoAnt/Shared) | Common helpers, ASP.NET Core, CSV and Mermaid utilities | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Shared?label=DragoAnt.Shared)](https://www.nuget.org/packages/DragoAnt.Shared) |
| [Extensions.T4](https://github.com/DragoAnt/Extensions.T4) | Utilities for generating code with T4 templates | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Extensions.T4?label=DragoAnt.Extensions.T4)](https://www.nuget.org/packages/DragoAnt.Extensions.T4) |

## Build tooling

- [MSBuildKit](https://github.com/DragoAnt/MSBuildKit) — build defaults, nuget.org-ready packaging, versioning from release tags, tests and coverage for .NET repositories.
- [MSBuild.Routine](https://github.com/DragoAnt/MSBuild.Routine) — the shared MSBuild files the DragoAnt repositories import as a submodule.
- [MonoRepo](https://github.com/DragoAnt/MonoRepo) — swaps `PackageReference` for `ProjectReference` to develop across several repositories at once.

## Contributing

Issues and pull requests are welcome — see the [contributing guide](https://github.com/DragoAnt/.github/blob/main/CONTRIBUTING.md). Report vulnerabilities privately as described in the [security policy](https://github.com/DragoAnt/.github/blob/main/SECURITY.md).
