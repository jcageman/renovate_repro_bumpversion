# renovate-packages-lock-bug

This repository showcases that renovate does not create correct PRs when
a dotnet project uses both central package versioning ([CentralPackageVersions](https://github.com/microsoft/MSBuildSdks/tree/main/src/CentralPackageVersions)) and uses https://docs.renovatebot.com/configuration-options/#bumpversion and has projects with a version attribute.

## What happens

Only the `.props` file containing the package version is updated. The `.csproj` version remains the same

## What should happen

Along with the `.props` file version update, all projects with a version tag should receive a patch update on their version.
