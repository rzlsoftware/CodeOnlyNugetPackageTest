# Code Only Nuget Package in WPF

## The Solution

Thanks to the help at [manuelroemer/Nullable#20](https://github.com/manuelroemer/Nullable/issues/20) I could find a solution to the problem.
The solution is described at [microsoft/CsWin32#7](https://github.com/microsoft/CsWin32/issues/7)

The referencing WPF project has to add the following property in the project:
```xml
<IncludePackageReferencesDuringMarkupCompilation>true</IncludePackageReferencesDuringMarkupCompilation>
```

## The Problem

A small test repository to play with source code only nuget packages in a WPF environment.

The `src\TheNugetPackage` projects is build by running
`dotnet build -c release src\TheNugetPackage\TheNugetPackage.csproj`
and creates a _Source code only Nuget package_ described in [that Medium article](https://medium.com/@attilah/source-code-only-nuget-packages-8f34a8fb4738) from [attila](https://github.com/attilah)

I tried to use that technic but when using it an an WPF environment i experienced problems.
Simply build open the soluion in Visual Studio, build the nuget package and then the WPF project.

If you undo the last commit or delete the empty `UserControl` the error will be gone.