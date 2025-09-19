# Csharpier Build Issue Reproduction

Run the following to view the error:

```bash
dotnet restore --force-evaluate \
  && dotnet build --no-incremental -v diag --tlp:default=false
```

If you remove the `xunit.v3` dependency, the error no longer occurs.

## The error

```
Build FAILED.

"/Users/danny/src/tdg5/csharpier-build-issue-reproduction/App.Tests.csproj" (Rebuild target) (1:7) ->
"/Users/danny/src/tdg5/csharpier-build-issue-reproduction/App.Tests.csproj" (CSharpierFormatInner target) (1:8) ->
 /usr/local/share/dotnet/sdk/9.0.300/Sdks/Microsoft.NET.Sdk/targets/Microsoft.NET.RuntimeIdentifierInference.targets(201,38): error MSB4184: The expression "[MSBuild]::VersionLessThan('', 6.0)" cannot be evaluated. Version string was not in a correct format. [/Users/danny/src/tdg5/csharpier-build-issue-reproduction/App.Tests.csproj]
```
