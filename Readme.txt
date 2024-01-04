# * Make sure Powershell Execution Policy is bypassed to run these scripts:
# * YOU MAY HAVE TO RUN THIS COMMAND PRIOR TO RUNNING THIS SCRIPT!
# Set-ExecutionPolicy Bypass -Scope Process
###############################################################################################
# First on teams General > Deploy Virtualbox  Machine Download "DownloadWindows2016_ISO.ps1"
# The Script "DownloadWindows2016_ISO.ps1" Downloads the image iso to deploy the VM
# Then from the same location on teams Download the "Deploy Virtual Machine.ps1"
# In powershell ISE open the script "Deploy Virtual Machine.ps1" and set the configuration for your VM
# Run the "Deploy Virtual Machine.ps1" and review deploy process of your VM
###############################################################################################
# In your Deployed VM Execute the following comand in powershell to download and install Chrome

$Path = $env:TEMP; $Installer = "chrome_installer.exe"; Invoke-WebRequest "http://dl.google.com/chrome/install/375.126/chrome_installer.exe" -OutFile $Path\$Installer; Start-Process -FilePath $Path\$Installer -Args "/silent /install" -Verb RunAs -Wait; Remove-Item $Path\$Installer

# In your Deployed VM, Download the Prerequisites needed for KS install - Copy and paste in your Installed chrome browser the following link
# https://ecisolutions.sharepoint.com/:u:/r/sites/KnowledgeSyncRD/Shared%20Documents/General/Deploy%20VirtualBox%20Machine/RequirementsKS.zip?csf=1&web=1&e=OpURN6