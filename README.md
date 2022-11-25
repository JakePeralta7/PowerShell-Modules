# PowerShell-Modules
 
## How to install a module
Open powershell as administrator and execute the following commands:
```powershell
Set-Location -Path <folder_of_zip>
Expand-Archive -Path <zip_name> -DestinationPath <module_name>
Copy-Item -Path <module_name> -Destination "C:\Program Files\WindowsPowerShell\Modules" -Recurse

# Importing the module
Import-Module -Name <module_name>

# Listing the module's exports
Get-Command -Module <module_name>
```