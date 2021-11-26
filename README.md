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
