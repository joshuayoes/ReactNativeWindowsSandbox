# React Native for Windows development setup

## Requirements

### Install `winget`
Installing `winget` is required to install the dependencies for this project. You can install it from the [Microsoft Store](https://www.microsoft.com/en-us/p/app-installer/9nblggh4nns1) or from [GitHub](https://github.com/microsoft/winget-cli?tab=readme-ov-file#installing-the-client)

#### Note for Windows Server users

If you are using Windows Server, you will need use PowerShell to install `winget`. [This is the offical way for Windows Sandbox](https://learn.microsoft.com/en-us/windows/package-manager/winget/#install-winget-on-windows-sandbox).

There are some known issues for Windows Server with the [offical Windows Sandbox approach](https://github.com/microsoft/winget-cli/issues/700). The alternative is using chocolatey to install `winget`:

Install at https://docs.chocolatey.org/en-us/choco/setup#installing-chocolatey-cli

Then run the following in PowerShell as an administrator

```powershell
choco install winget
```

## How to use

1. Clone the repository
2. Open a PowerShell window in the root of the repository
3. Run `winget configure ./ReactNativeWindows.dsc.yaml`. This will setup required dependencies.
4. Run `winget configure ./WindowsDevTools.dsc.yaml`. This will setup development tools you probably want to work with using React Native for Windows. 
