# .NET 9.0 Upgrade Report

## Project modifications

| Project name                                   | Old Target Framework    | New Target Framework         | Commits                   |
|:-----------------------------------------------|:-----------------------:|:----------------------------:|---------------------------|
| src/BlazorShared/BlazorShared.csproj           |   net6.0                | net9.0                       | 55a51c53                  |
| src/ApplicationCore/ApplicationCore.csproj     |   net6.0                | net9.0                       | ae78594a, cf563962         |
| src/Infrastructure/Infrastructure.csproj       |   net6.0                | net9.0                       | 5e0395c3, 9f231422         |
| src/BlazorAdmin/BlazorAdmin.csproj             |   net6.0                | net9.0                       | 3b6467c8, e2dd62d0         |
| src/Web/Web.csproj                             |   net6.0                | net9.0                       | b35311b2, f2d5dbcd         |
| src/PublicApi/PublicApi.csproj                 |   net6.0                | net9.0                       | cb661229, bb34ec92         |
| tests/UnitTests/UnitTests.csproj               |   net6.0                | net9.0                       | 6d52000d, 920f6369         |
| tests/IntegrationTests/IntegrationTests.csproj |   net6.0                | net9.0                       | 00fe3163, 9add8802         |

## NuGet Packages

| Package Name                        | Old Version | New Version | Commit Id                                 |
|:------------------------------------|:-----------:|:-----------:|-------------------------------------------|
| System.Text.Json                    |   6.0.5     |  9.0.4      | cf563962                                  |
| System.Security.Claims              |   4.3.0     |  (removed)  | cf563962                                  |
| Microsoft.AspNetCore.Identity.EntityFrameworkCore | 6.0.8 | 9.0.4 | 9f231422, f2d5dbcd, bb34ec92              |
| Microsoft.EntityFrameworkCore.InMemory | 6.0.8 | 9.0.4 | 9f231422, f2d5dbcd, bb34ec92, 9add8802     |
| Microsoft.EntityFrameworkCore.SqlServer | 6.0.8 | 9.0.4 | 9f231422, f2d5dbcd, bb34ec92               |
| System.IdentityModel.Tokens.Jwt     | 6.23.0      |  8.9.0      | 9f231422, f2d5dbcd, bb34ec92              |
| Microsoft.AspNetCore.Components.Authorization | 6.0.8 | 9.0.4 | e2dd62d0                                  |
| Microsoft.AspNetCore.Components.WebAssembly | 6.0.8 | 9.0.4 | e2dd62d0                                  |
| Microsoft.AspNetCore.Components.WebAssembly.Authentication | 6.0.8 | 9.0.4 | e2dd62d0                                  |
| Microsoft.AspNetCore.Components.WebAssembly.DevServer | 6.0.8 | 9.0.4 | e2dd62d0                                  |
| Microsoft.Extensions.Identity.Core  | 6.0.8       |  9.0.4      | e2dd62d0                                  |
| Microsoft.Extensions.Logging.Configuration | 6.0.0 | 9.0.4 | e2dd62d0                                  |
| System.Net.Http.Json                | 6.0.0       |  9.0.4      | e2dd62d0                                  |
| Microsoft.AspNetCore.Authentication.JwtBearer | 6.0.8 | 9.0.4 | f2d5dbcd, bb34ec92                        |
| Microsoft.AspNetCore.Components.WebAssembly.Server | 6.0.8 | 9.0.4 | f2d5dbcd                                  |
| Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore | 6.0.8 | 9.0.4 | f2d5dbcd, bb34ec92                       |
| Microsoft.AspNetCore.Identity.UI     | 6.0.8       |  9.0.4      | f2d5dbcd, bb34ec92                        |
| Microsoft.EntityFrameworkCore.Tools  | 6.0.8       |  9.0.4      | f2d5dbcd, bb34ec92                        |
| Microsoft.VisualStudio.Web.CodeGeneration.Design | 6.0.8 | 9.0.0 | f2d5dbcd, bb34ec92                        |
| Microsoft.VisualStudio.Azure.Containers.Tools.Targets | 1.17.0 | (removed) | bb34ec92                                 |
| Microsoft.AspNetCore.Mvc             | 2.2.0       |  2.3.0      | 920f6369                                  |

## All commits

| Commit ID   | Description                                |
|:------------|:-------------------------------------------|
| 55a51c53    | Update BlazorShared.csproj to target .NET 9.0 |
| ae78594a    | Upgrade target framework in ApplicationCore.csproj |
| cf563962    | Update dependencies in ApplicationCore.csproj |
| 5e0395c3    | Update target framework in Infrastructure.csproj |
| 9f231422    | Update package versions in Infrastructure.csproj |
| 3b6467c8    | Upgrade BlazorAdmin.csproj to .NET 9.0         |
| e2dd62d0    | Update package versions in BlazorAdmin.csproj   |
| b35311b2    | Upgrade target framework in Web.csproj         |
| f2d5dbcd    | Update package versions in Web.csproj          |
| cb661229    | Upgrade target framework in PublicApi.csproj   |
| bb34ec92    | Update package versions in PublicApi.csproj    |
| 6d52000d    | Update UnitTests.csproj to target .NET 9.0     |
| 920f6369    | Update UnitTests.csproj to use Microsoft.AspNetCore.Mvc 2.3.0 |
| 00fe3163    | Upgrade target framework in IntegrationTests.csproj |
| 9add8802    | Update IntegrationTests.csproj to upgrade EF Core package |

## Test Results

- UnitTests: 44 passed, 0 failed, 0 skipped
- IntegrationTests: 3 passed, 0 failed, 0 skipped

## Next steps

- Review your application for any runtime issues or breaking changes.
- Test all application scenarios in your staging environment.
- Monitor for any issues after deployment to production.
