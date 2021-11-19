# ClickOncePowershell
Run the ClickOnce MAGE tool from a powershell script.

## The problem

There are a number of steps involved in creating a ClickOnce release, some of which are supported by MAGE, some through MSBuild &lt;GenerateDeploymentManifest&gt;, some through MageUI.

This script brings together all those features into one.

## Usage

Set up the following folder structure:

```
Root
  \- App
  \- Website
     \- App
  \- Launcher
  \- ClickOncePS
```

- Root\App contains your application's EXEs and DLLs
- Website contains your web.config
- Launcher contains your custom Launcher.exe (if you are using one)
- ClickOncePS should contain this script and your .pfx certificate
- Website\App is the output folder.

## Build details

The clickonce version number is taken from your application EXE's version, so this must be accurate.
Alternatively you could modify the script to take the version as a parameter.

## Run the script

```
cd ClickOncePS
.\CreateClickOnce.ps1 -url 'http://yoursite' -id 'yourappname' -title 'App title'
```
  
Website\App will be populated with the .deploy, .manifest and .application files.


