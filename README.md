# React Native for Windows development setup

This project contains [WinGet Configurations](https://learn.microsoft.com/en-us/windows/package-manager/configuration/) that can install all of the [System Requirements for React Native for Windows](https://microsoft.github.io/react-native-windows/docs/rnw-dependencies). I found that the [rnw-dependencies.ps1](https://aka.ms/rnw-vs2022-deps.ps1) powershell script from the official docs was helpful for debugging if an Windows machine was configured correctly but the auto install options seemed to fail consistently on my machines. 

## Requirements

### Install `winget`
If you are using Windows 11, you are done! It's already installed. If you are on Windows 11, tou can install it from the [Microsoft Store](https://www.microsoft.com/en-us/p/app-installer/9nblggh4nns1) or from [GitHub](https://github.com/microsoft/winget-cli?tab=readme-ov-file#installing-the-client)

<details>
  <summary>Note for Windows Server users</summary>

If you are using Windows Server, you will need use PowerShell to install `winget`. [This is the offical way for Windows Sandbox](https://learn.microsoft.com/en-us/windows/package-manager/winget/#install-winget-on-windows-sandbox).

There are some known issues for Windows Server with the [offical Windows Sandbox approach](https://github.com/microsoft/winget-cli/issues/700). The alternative is using chocolatey to install `winget`:

Install at https://docs.chocolatey.org/en-us/choco/setup#installing-chocolatey-cli

Then run the following in PowerShell as an administrator

```powershell
choco install winget
```
</details>

## How to run

### `powershell` method

1. Open Powershell terminal **as administrator**
2. Run `Invoke-WebRequest -Uri "https://raw.githubusercontent.com/joshuayoes/ReactNativeWindowsSandbox/main/ReactNativeWindows.dsc.yaml" -OutFile "ReactNativeWindows.dsc.yaml"`. This will download `ReactNativeWindows.dsc.yaml` to your working directory.
3. Run `winget configure ReactNativeWindows.dsc.yaml`. This will setup required dependencies.
4. Run `Invoke-WebRequest -Uri "https://raw.githubusercontent.com/joshuayoes/ReactNativeWindowsSandbox/main/WindowsDevTools.dsc.yaml" -OutFile "WindowsDevTools.dsc.yaml"`. This will download `WindowsDevTools.dsc.yaml` to your working directory.
5. Run `winget configure WindowsDevTools.dsc.yaml`. This will setup development tools you probably want to work with using React Native for Windows.

### `git clone` method

1. Clone the repository
2. Open a PowerShell window in the root of the repository **as administrator**
3. Run `winget configure ReactNativeWindows.dsc.yaml`. This will setup required dependencies.
4. Run `winget configure WindowsDevTools.dsc.yaml`. This will setup development tools you probably want to work with using React Native for Windows. 

