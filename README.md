# DSC: .NET Environment Setup with Winget

This project provides configurations for setting up .NET  development environments using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) on Windows.

## Prerequisites
- Windows 10 (1809+) or Windows 11
- [winget](https://aka.ms/getwingetpreview) (Windows Package Manager) installed

## Installation
1. Download and install the latest version of winget from [https://aka.ms/getwingetpreview](https://aka.ms/getwingetpreview).
2. Open an **administrative PowerShell** or Command Prompt.
3. Enable experimental features in winget:

   Run the following command to open the winget settings file:
   
   ```powershell
   winget settings
   ```
   
   Add or update the configuration file with the following content:
   
   ```json
   {
       "$schema": "https://aka.ms/winget-settings.schema.json",
       // For documentation on these settings, see: https://aka.ms/winget-settings
       "experimentalFeatures": {
           "dependencies": true,
           "directMSI": false,
           "zipInstall": false,
           "configureExport": true
       },
       "visual": {
           "progressBar": "rainbow"
       },
       "source": {
           "autoUpdateIntervalInMinutes": 5
       },
       "installBehavior": {
           "preferences": {
               "scope": "machine" // or "user"
           }
       }
   }
   ```
   
   For more details, see the [winget settings documentation](https://aka.ms/winget-settings).

### Install core components
Run the following command to apply the core computer components:

```powershell
winget configure -f setup.winget
```
> **setup.winget**: Contains a [winget configuration](https://learn.microsoft.com/en-us/windows/package-manager/configuration/) for installing and configuring core windows settings and related tools.

### For .NET Development
Run the following command to apply the .NET configuration:

```powershell
winget configure -f dotnet.winget
```
> **dotnet.winget**: Contains a [winget configuration](https://learn.microsoft.com/en-us/windows/package-manager/configuration/) for installing and configuring .NET, Visual Studio, Azure CLI, Node.js, and related tools.

### Helpful windows apps
Run the following command to install some helpfull windows apps  like Spotify, Slack, etc
This needs to be  run in a non-administrator prompt (slack won't install otherwise)

```powershell
winget configure -f apps.winget
```
> **apps.winget**: Contains a [winget configuration](https://learn.microsoft.com/en-us/windows/package-manager/configuration/) for installing and configuring Slack, Spotify, and simular apps.


## Usage
- To re-apply or update a configuration, simply run the install command again for the desired environment.
- You can edit the `.winget` files to include additional packages or settings.

## Troubleshooting
- Ensure you are running the console as an administrator (not for **apps.winget**).
- If you encounter issues with winget, check for updates or reinstall from the official link above.
- For more help, see the [winget documentation](https://learn.microsoft.com/en-us/windows/package-manager/winget/).


## References
- [Winget DSC Sample Configurations](https://github.com/microsoft/winget-dsc/tree/main/samples)
- [Visual Studio Workload and Component IDs](https://learn.microsoft.com/en-us/visualstudio/install/workload-and-component-ids?view=vs-2026)
- [Enable Your Device for Development](https://learn.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development)

## Winget Repositories
- [winget.run](https://winget.run/)
- [winstall.app](https://winstall.app/)

## Oh My Posh Configuration
For detailed instructions on setting up and customizing your prompt with Oh My Posh (installed automatically via `tools.winget`), see the [Oh My Posh Configuration Guide](./oh-my-posh.md).
