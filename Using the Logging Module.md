# Using the Logging Module

After installing the Logging module, you can use it in your scripts to make debugging and troubleshooting easy.

## Use case
```powershell
# Importing the logging module
Import-Module -Name Logging

# Logging levels 'DEBUG', 'INFO', 'WARNING', 'ERROR'

# Choosing the default verbosity of the logging
Set-LoggingDefaultLevel -Level INFO

# Setting targets for logging
Add-LoggingTarget -Name Console -Configuration @{Level = 'DEBUG'}
Add-LoggingTarget -Name File -Configuration @{Level = 'INFO'; Path = "$($env:USERPROFILE)\Desktop\example_%{+%Y%m%d}.log"}

Write-Log -Level DEBUG -Message "Message from $($env:COMPUTERNAME)"
Wait-Logging
```

To list all available targets, use `Get-LoggingAvailableTarget`

## Creating new logging levels
You can create new level like this
```powershell
Add-LoggingLevel -Level <number> -LevelName <string>
```
The highest the number is - the least verbose