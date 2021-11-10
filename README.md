# ASP codegen setup

```sh
dotnet tool install --global dotnet-aspnet-codegenerator --version 5.0.2
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 5.0.2
#<PackageReference Include="Microsoft.VisualStudio.Web.CodeGeneration.Design" Version="5.0.2" />
```
# Generate controller

```sh
dotnet-aspnet-codegenerator.exe controller -async -api -outDir Controllers -name MyController
```
