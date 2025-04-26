@echo off
title Install Tools to Make Windows 11 Look Like Windows 10

:: Create a temp directory for the downloads
mkdir %USERPROFILE%\Downloads\Windows10Look

:: Change to that directory
cd %USERPROFILE%\Downloads\Windows10Look

echo Downloading Open-Shell...
:: Download Open-Shell from GitHub
powershell -Command "Invoke-WebRequest https://github.com/Open-Shell/Open-Shell-Menu/releases/download/v4.4.170/OpenShell_4_4_170.exe -OutFile OpenShellSetup.exe"

echo Downloading OldNewExplorer...
:: Download OldNewExplorer (Classic File Explorer)
powershell -Command "Invoke-WebRequest https://www.msfn.org/board/applications/core/interface/file/attachment.php?id=27271 -OutFile OldNewExplorerSetup.exe"

echo Downloading StartAllBack (Optional, Paid)...
:: If you want to include StartAllBack, uncomment the next line and make sure you have a valid license key
::powershell -Command "Invoke-WebRequest https://github.com/StartAllBack/StartAllBack/releases/download/v2.9.0/StartAllBackSetup.exe -OutFile StartAllBackSetup.exe"

:: Now install the tools
echo Installing Open-Shell...
start /wait OpenShellSetup.exe /S

echo Installing OldNewExplorer...
start /wait OldNewExplorerSetup.exe /S

:: If you downloaded StartAllBack, install it as well (uncomment the next line)
::start /wait StartAllBackSetup.exe /S

:: Configuring Open-Shell (Windows 10 style Start Menu)
echo Configuring Open-Shell...
:: Open-Shell auto configuration is not directly possible via batch file, but we can apply default settings
:: You will need to manually configure Open-Shell later (choose Classic with two columns or Windows 7 style).

:: If you want to modify Open-Shell settings further, you will have to edit the config file manually:
:: The settings are stored at: %APPDATA%\OpenShell\OpenShell.ini

:: Applying OldNewExplorer settings for classic file explorer
echo Configuring OldNewExplorer...
:: OldNewExplorer settings are stored in the registry, we will tweak the registry to apply classic settings

reg add "HKCU\Software\OldNewExplorer" /v "EnableClassicExplorer" /t REG_DWORD /d 1 /f
reg add "HKCU\Software\OldNewExplorer" /v "UseClassicToolbar"
