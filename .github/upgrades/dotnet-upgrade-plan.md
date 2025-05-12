# .NET 9.0 Upgrade Plan

## Execution Steps

1. Validate that a .NET 9.0 SDK required for this upgrade is installed on the machine and if not, help to get it installed.
2. Ensure that the SDK version specified in global.json files is compatible with the .NET 9.0 upgrade.
3. Upgrade projects to .NET 9.0.
  - 3.1. Upgrade src/BlazorShared/BlazorShared.csproj
  - 3.2. Upgrade src/ApplicationCore/ApplicationCore.csproj
  - 3.3. Upgrade src/Infrastructure/Infrastructure.csproj
  - 3.4. Upgrade src/BlazorAdmin/BlazorAdmin.csproj
  - 3.5. Upgrade src/Web/Web.csproj
  - 3.6. Upgrade tests/UnitTests/UnitTests.csproj
  - 3.7. Upgrade src/PublicApi/PublicApi.csproj
  - 3.8. Upgrade tests/IntegrationTests/IntegrationTests.csproj
4. Run unit tests to validate upgrade
  - tests/UnitTests/UnitTests.csproj
  - tests/IntegrationTests/IntegrationTests.csproj

## Settings

This section contains settings and data used by execution steps.

### Excluded projects

| Project name | Description |
|:-----------------------------------------------|:---------------------------:|

### Aggregate NuGet packages modifications across all projects

NuGet packages used across all selected projects or their dependencies that need version update in projects that reference them.

| Package Name | Current Version | New Version | Description |
|:------------------------------------|:---------------:|:-----------:|:------------------------------------|
| Microsoft.AspNetCore.Authentication.JwtBearer | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Components.Authorization | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Components.WebAssembly | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Components.WebAssembly.Authentication | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Components.WebAssembly.DevServer | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Components.WebAssembly.Server | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Identity.EntityFrameworkCore | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.AspNetCore.Identity.UI | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.EntityFrameworkCore.InMemory | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.EntityFrameworkCore.SqlServer | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.EntityFrameworkCore.Tools | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.Extensions.Identity.Core | 6.0.8 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.Extensions.Logging.Configuration | 6.0.0 | 9.0.5 | Recommended for .NET 9.0 |
| Microsoft.VisualStudio.Web.CodeGeneration.Design | 6.0.8 | 9.0.0 | Recommended for .NET 9.0 |
| System.IdentityModel.Tokens.Jwt | 6.23.0 | 8.9.0 | Security vulnerability, deprecated |
| System.Net.Http.Json | 6.0.0 | 9.0.5 | Recommended for .NET 9.0 |
| System.Security.Claims | 4.3.0 | (remove) | Functionality included with framework reference |
| System.Text.Json | 6.0.5 | 9.0.5 | Security vulnerability |
| Microsoft.VisualStudio.Azure.Containers.Tools.Targets | 1.17.0 | (remove) | Incompatible with .NET 9.0 |
| Microsoft.AspNetCore.Mvc | 2.2.0 | 2.3.0 | Deprecated |
| Blazored.LocalStorage | 4.2.0 | 4.5.0 | |

### Project upgrade details

#### src/BlazorShared/BlazorShared.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`

#### src/ApplicationCore/ApplicationCore.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - System.Security.Claims should be removed (functionality included with framework reference)
  - System.Text.Json should be updated from `6.0.5` to `9.0.5` (*security vulnerability*)

#### src/Infrastructure/Infrastructure.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.AspNetCore.Identity.EntityFrameworkCore should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.InMemory should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.SqlServer should be updated from `6.0.8` to `9.0.5`
  - System.IdentityModel.Tokens.Jwt should be updated from `6.23.0` to `8.9.0` (*security vulnerability, deprecated*)

#### src/BlazorAdmin/BlazorAdmin.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.AspNetCore.Components.Authorization should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Components.WebAssembly should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Components.WebAssembly.Authentication should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Components.WebAssembly.DevServer should be updated from `6.0.8` to `9.0.5`
  - Microsoft.Extensions.Identity.Core should be updated from `6.0.8` to `9.0.5`
  - Microsoft.Extensions.Logging.Configuration should be updated from `6.0.0` to `9.0.5`
  - System.Net.Http.Json should be updated from `6.0.0` to `9.0.5`

#### src/Web/Web.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.AspNetCore.Components.WebAssembly.Server should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.InMemory should be updated from `6.0.8` to `9.0.5`
  - Microsoft.VisualStudio.Web.CodeGeneration.Design should be updated from `6.0.8` to `9.0.0`
  - Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Identity.EntityFrameworkCore should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Identity.UI should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.SqlServer should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Authentication.JwtBearer should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.Tools should be updated from `6.0.8` to `9.0.5`
  - System.IdentityModel.Tokens.Jwt should be updated from `6.23.0` to `8.9.0` (*security vulnerability, deprecated*)

#### tests/UnitTests/UnitTests.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.AspNetCore.Mvc should be updated from `2.2.0` to `2.3.0` (*deprecated*)

#### src/PublicApi/PublicApi.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.AspNetCore.Authentication.JwtBearer should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Identity.EntityFrameworkCore should be updated from `6.0.8` to `9.0.5`
  - Microsoft.AspNetCore.Identity.UI should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.InMemory should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.SqlServer should be updated from `6.0.8` to `9.0.5`
  - Microsoft.EntityFrameworkCore.Tools should be updated from `6.0.8` to `9.0.5`
  - Microsoft.VisualStudio.Web.CodeGeneration.Design should be updated from `6.0.8` to `9.0.0`
  - System.IdentityModel.Tokens.Jwt should be updated from `6.23.0` to `8.9.0` (*security vulnerability, deprecated*)
  - Microsoft.VisualStudio.Azure.Containers.Tools.Targets should be removed (incompatible with .NET 9.0)

#### tests/IntegrationTests/IntegrationTests.csproj modifications
Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`
NuGet packages changes:
  - Microsoft.EntityFrameworkCore.InMemory should be updated from `6.0.8` to `9.0.5`
