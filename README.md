# Dev Container for Microsoft 365 Admins

[![View on GitHub Container Registry](https://img.shields.io/badge/View%20on-GitHub%20Container%20Registry-blue?logo=github)](https://ghcr.io/workoho/devcontainers/m365-admin)
[![Build Docker Image](https://github.com/workoho/devcontainer-image-m365-admin/actions/workflows/BUILD-01_build-push-devcontainer-image.yml/badge.svg)](https://github.com/workoho/devcontainer-image-m365-admin/actions/workflows/BUILD-01_build-push-devcontainer-image.yml)

## Summary

_This repository contains the build data for a custom devcontainer image, dedicated to Microsoft 365 Admins._

| Metadata                                                | Value                                                |
| ------------------------------------------------------- | ---------------------------------------------------- |
| _Categories_                                            | Other                                                |
| _Image type_                                            | Dockerfile                                           |
| _Published images_                                      | [`ghcr.io/workoho/devcontainers/m365-admin`][1]      |
| [_Available image variants_](#available-image-variants) | `latest`, `v1`, `weekly` ([full list][2])            |
| _Published image architecture(s)_                       | `x86-64`, `aarch64/arm64`                            |
| _Container host OS support_                             | Linux, macOS, Windows                                |
| _Container OS_                                          | [devcontainers/base:ubuntu][3]                       |
| _Languages, platforms_                                  | PowerShell [`7.4` (LTS)][4], Node.js [`20` (LTS)][5] |

[1]: https://ghcr.io/workoho/devcontainers/m365-admin
[2]: https://github.com/workoho/devcontainer-image-m365-admin/pkgs/container/devcontainers%2Fm365-admin/versions?filters%5Bversion_type%5D=tagged
[3]: https://github.com/devcontainers/images/tree/main/src/base-ubuntu
[4]: https://learn.microsoft.com/en-us/powershell/scripting/install/powershell-support-lifecycle
[5]: https://nodejs.org/en/about/previous-releases

## Using this image

### GitHub Codespaces

**We recommend you start with our [GitHub Codespace template](https://github.com/workoho/codespace-m365-admin)**,
which comes with pre-selected settings and extensions:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/workoho/codespace-m365-admin)
[![Create my Own Codespace](https://img.shields.io/badge/Create-My%20Own%20Codepsace-green?style=for-the-badge)](https://github.com/workoho/codespace-m365-admin/generate)

### Dev Container Template

Alternatively, there is a Dev Container Template available to create your own dev container, based on this image:

[![Go to Dev Container Template](https://img.shields.io/badge/Go%20To-Dev%20Container%20Template-blue?style=for-the-badge)](https://github.com/workoho/devcontainer-templates/tree/main/src/m365-admin)

See [Create a Dev Container](https://code.visualstudio.com/docs/devcontainers/create-dev-container) to learn more.

### Available Image Variants

The `ghcr.io/workoho/devcontainers/m365-admin` image offers several tags, catering to different needs for stability, updates,
and development cycles, as outlined below:

| Image Variant Tag  | Update Cycle     | Description                                                                                                                                                                                                                           |
| ------------------ | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `latest`           | As needed        | Automatically tracks the most stable version, typically aligning with the `v1` tag. Ideal for users seeking stability with recent features.                                                                                           |
| `weekly`           | Weekly (Mondays) | A snapshot of the `main` branch as of the last automated build cycle, providing a regular, stable update rhythm. Suitable for environments that benefit from weekly updates without needing immediate changes from the `main` branch. |
| `main`             | As needed        | Reflects the current state of the main development branch. This tag is updated with manual builds for testing or immediate updates, offering the latest developments at any given time.                                               |
| `v1`               | As needed        | Tracks the latest updates within the major version 1, offering a balance between stability and new features. Recommended for most users.                                                                                              |
| `v1.x`             | As needed        | Targets a specific minor version within the major version 1, receiving only bug fixes and patches. Ideal for environments requiring minimal changes.                                                                                  |
| `1.x.x`            | Fixed            | Specifies an exact version for maximum stability. This tag does not receive updates, making it suitable for critical environments.                                                                                                    |
| `1.x.x-prerelease` | As needed        | Points to a specific pre-release version for testing or development purposes, where the latest features are needed despite potential instability.                                                                                     |

### Choosing the Right Tag

To use a specific image variant, modify the image URI in your Docker command like so:

```bash
docker pull ghcr.io/workoho/devcontainers/m365-admin:<TAG>
```

Visit the [Container Registry versions page][2] to scroll through the currently available tags.

## Pre-installed Software

### PowerShell Modules

This image comes pre-equipped with the following PowerShell modules:

| Module                        |     Version Tree     | Resource Link                                                                                          |
| ----------------------------- | :------------------: | ------------------------------------------------------------------------------------------------------ |
| [Azure Az][6]                 |       `12.1.x`       | [GitHub](https://github.com/Azure/azure-powershell)                                                    |
| [ExchangeOnlineManagement][7] |       `3.5.x`        | [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange/ct-p/Exchange)              |
| [Microsoft.Graph][8]          |       `2.20.x`       | [GitHub](https://github.com/microsoftgraph/msgraph-sdk-powershell)                                     |
| [Microsoft.Graph.Entra][9]    | `0.12.x-preview`[^1] | [GitHub](https://github.com/microsoftgraph/entra-powershell)                                           |
| [MicrosoftTeams][10]          |       `6.4.x`        | [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams/ct-p/MicrosoftTeams) |

For a complete list of Microsoft related PowerShell modules, use the [PowerShell Module Browser](https://learn.microsoft.com/en-us/powershell/module/).

[6]: https://learn.microsoft.com/en-us/powershell/azure/new-azureps-module-az
[7]: https://learn.microsoft.com/en-us/powershell/exchange/exchange-online-powershell
[8]: https://learn.microsoft.com/en-us/powershell/microsoftgraph/?view=graph-powershell-1.0
[9]: https://learn.microsoft.com/en-us/powershell/entra-powershell/?view=entra-powershell
[10]: https://learn.microsoft.com/en-us/microsoftteams/teams-powershell-overview

### PowerShell Utilities

This image comes pre-equipped with the following PowerShell complementary utilities for basic scripting:

| Module                            | Version Tree | Resource Link                                                                                              |
| --------------------------------- | :----------: | ---------------------------------------------------------------------------------------------------------- |
| [Crescendo][11]                   |   `1.1.x`    | [GitHub/PowerShell/Crescendo](https://github.com/PowerShell/Crescendo)                                     |
| [PSScriptAnalyzer][12]            | `latest`[^2] | [GitHub/PowerShell/PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer)                       |
| [SecretManagement][13]            |   `1.1.x`    | [GitHub/PowerShell/SecretManagement](https://github.com/PowerShell/SecretManagement)                       |
| [SecretStore][13]                 |   `1.0.x`    | [GitHub/PowerShell/SecretStore](https://github.com/PowerShell/SecretStore)                                 |
| [TextUtility][14]                 |   `0.1.x`    | [GitHub/PowerShell/TextUtility](https://github.com/PowerShell/TextUtility)                                 |

[11]: https://learn.microsoft.com/en-us/powershell/utility-modules/crescendo/overview
[12]: https://learn.microsoft.com/en-us/powershell/utility-modules/psscriptanalyzer/overview
[13]: https://learn.microsoft.com/en-us/powershell/utility-modules/secretmanagement/overview
[14]: https://devblogs.microsoft.com/powershell/microsoft-powershell-textutility-module-updates/

## Other Image Flavors

There are other flavors of this dev container image available:

| Flavor                                                                                                | Audience                                                                 |
| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [🧑‍💻 Development Container for Microsoft 365](https://github.com/workoho/devcontainer-image-m365-dev)   | An image dedicated to Microsoft 365 Developers and Sophisticated Admins. |
| [🧑‍🔧 Ultimate Container for Microsoft 365](https://github.com/workoho/devcontainer-image-m365-ultimate) | An image dedicated to Holistic Microsoft 365 & Azure Professionals. |

## License

Copyright © Workoho GmbH. All rights reserved.

Licensed under the MIT License. See [LICENSE.txt](https://github.com/workoho/devcontainer-image-m365-admin/blob/main/LICENSE.txt)


[^1]: Any new version up to the next minor version of the upcoming major release is installed without further validation of the container image maintainers.

[^2]: As provided by the [PowerShell Visual Studio Code extension](https://code.visualstudio.com/docs/languages/powershell/).
