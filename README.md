# Environment variables
Get path
```ps1
[System.Environment]::GetEnvironmentVariable("Path",[System.EnvironmentVariableTarget]::User)
```

Set path
```ps1
[System.Environment]::SetEnvironmentVariable("Path","Value",[System.EnvironmentVariableTarget]::User])
```

Add path Windows
```ps1
[System.Environment]::SetEnvironmentVariable(
"Path",
"$([System.Environment]::GetEnvironmentVariable("Path",[System.EnvironmentVariableTarget]::User));NewValue",
[System.EnvironmentVariableTarget]::User)
```

# ASP codegen setup

```sh
dotnet tool install --global dotnet-aspnet-codegenerator --version 5.0.2
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 5.0.2
#<PackageReference Include="Microsoft.VisualStudio.Web.CodeGeneration.Design" Version="5.0.2" />
```
# Generate controller

```sh
dotnet-aspnet-codegenerator controller -async -api -outDir Controllers -name MyController
```

# Publish single file executable
```sh
 dotnet publish -r win-x64 -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true --self-contained true
```

# Entity Framework Core migration + update

```sh
dotnet ef migrations add MigrationName
dotnet ef database update
```


# ASP.NET api with codegen
```ps1
# Create project
dotnet new webapi
# Install required
dotnet tool install --global dotnet-aspnet-codegenerator --version 6.0.2
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 6.0.2
dotnet tool install --global dotnet-ef
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SQLite
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer

dotnet-aspnet-codegenerator controller `
-name NameController `
-m ModelClassName `
-dc MyDataContext `
--relativeFolderPath Controllers `
--useDefaultLayout `
--referenceScriptLibraries `
-sqlite `
--restWithNoViews
```
