# DragoAnt

Small, focused .NET libraries — MIT-licensed, published on [nuget.org](https://www.nuget.org/profiles/DragoAnt), built with one shared toolchain.

## Packages

| Repository | What it is | NuGet |
| --- | --- | --- |
| [Extensions.System.Text.Json](https://github.com/DragoAnt/Extensions.System.Text.Json) | Mask or extract JSON values by property-path rules in one streaming pass, no DOM. `Observer` for any JSON, `Observer.Http` for request/response bodies; ships [agent skills](https://github.com/DragoAnt/Extensions.System.Text.Json/blob/main/docs/skills.md) for AI coding assistants. | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.System.Text.Json.Observer)](https://www.nuget.org/packages/DragoAnt.System.Text.Json.Observer) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.System.Text.Json.Observer)](https://www.nuget.org/packages/DragoAnt.System.Text.Json.Observer) |
| [SerilogSinksInMemory](https://github.com/vfofanov/SerilogSinksInMemory) | Serilog in-memory sink for tests, with log assertions for FluentAssertions, AwesomeAssertions and Shouldly; `DragoAnt.Assertions` is the framework-agnostic adapter layer underneath. | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Serilog.Sinks.InMemory)](https://www.nuget.org/packages/DragoAnt.Serilog.Sinks.InMemory) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.Serilog.Sinks.InMemory)](https://www.nuget.org/packages/DragoAnt.Serilog.Sinks.InMemory) |
| [Extensions.DependencyInjection](https://github.com/DragoAnt/Extensions.DependencyInjection) | Source generator: attributes turn into `IServiceCollection` registrations and factories at compile time. | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Extensions.DependencyInjection)](https://www.nuget.org/packages/DragoAnt.Extensions.DependencyInjection) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.Extensions.DependencyInjection)](https://www.nuget.org/packages/DragoAnt.Extensions.DependencyInjection) |
| [Shared](https://github.com/DragoAnt/Shared) | Helpers for text building, CSV, ASP.NET Core and a C# builder for Mermaid flowcharts. | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Shared)](https://www.nuget.org/packages/DragoAnt.Shared) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.Shared)](https://www.nuget.org/packages/DragoAnt.Shared) |
| [Extensions.T4](https://github.com/DragoAnt/Extensions.T4) | Base class and helpers for runtime T4 templates with a typed data model. | [![NuGet](https://img.shields.io/nuget/v/DragoAnt.Extensions.T4)](https://www.nuget.org/packages/DragoAnt.Extensions.T4) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.Extensions.T4)](https://www.nuget.org/packages/DragoAnt.Extensions.T4) |
| [Extensions.EntityFrameworkCore](https://github.com/DragoAnt/Extensions.EntityFrameworkCore) | **Beta.** Static and historical migrations, entity conventions and entity definitions for EF Core (SQL Server, PostgreSQL). | [![NuGet](https://img.shields.io/nuget/vpre/DragoAnt.EntityFrameworkCore)](https://www.nuget.org/packages/DragoAnt.EntityFrameworkCore) [![Downloads](https://img.shields.io/nuget/dt/DragoAnt.EntityFrameworkCore)](https://www.nuget.org/packages/DragoAnt.EntityFrameworkCore) |

## How the packages are built

[MSBuildKit](https://github.com/DragoAnt/MSBuildKit) [![Release](https://img.shields.io/github/v/release/DragoAnt/MSBuildKit)](https://github.com/DragoAnt/MSBuildKit/releases) — shared MSBuild settings committed as plain files: nuget.org-ready package metadata with build-time checks, versions from release tags, Microsoft.Testing.Platform tests with coverage. Extensions.System.Text.Json builds with it and the shared CI workflow in [DragoAnt/.github](https://github.com/DragoAnt/.github); the other repositories are moving over.

<!-- Support the work: add a line here once .github/FUNDING.yml exists. -->

## Contributing

Issues and pull requests are welcome — see the [contributing guide](https://github.com/DragoAnt/.github/blob/main/CONTRIBUTING.md). Report vulnerabilities privately as described in the [security policy](https://github.com/DragoAnt/.github/blob/main/SECURITY.md).
