# cordova-windows-empty-lib
A small plugin adding an empty Portable class library in order to problem with Windows Phone 8.1 enterprise deployement.


## Initial issue
Cordova generates a Javascript based projet when targeting Windows Phone with windows target.
Using this kind projet has a side effect LOB application, signed with an enterprise certificate preventing application form being installed on actual phones.

## Solution
This plugin adds a simple DLL (without any logic) in order to trigger processes that enable this kind of deployement.

## Installation

    cordova plugin add cordova-windows-empty-lib

## Compilation example : 

    cordova build windows --target=phone --release
    powershell.exe -File "C:\Program Files (x86)\Microsoft SDKs\WindowsPhoneApp\v8.1\Tools\MDILXAPCompile\BuildMDILAPPX.ps1" -appxfilename .\platforms\windows\AppPackages\CordovaApp.Windows_1.0.0.0_anycpu_Test\CordovaApp.Windows_1.0.0.0_anycpu.appx -pfxfilename .\hereliesmycertificate\certificate.pfx -password myPassword