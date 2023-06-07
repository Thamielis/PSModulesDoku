New-CMScript
------------




### Synopsis
Create a PowerShell script in Configuration Manager.



---


### Description

Use this cmdlet to create a new PowerShell script. These scripts are integrated and managed in Configuration Manager.



For more information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMScript](Approve-CMScript)



* [Deny-CMScript](Deny-CMScript)



* [Get-CMScript](Get-CMScript)



* [Invoke-CMScript](Invoke-CMScript)



* [Remove-CMScript](Remove-CMScript)



* [Set-CMScript](Set-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Create a script with text
```PowerShell
New-CMScript -ScriptName "CMScript" -ScriptText 'Write-Host "New Script"'
```

#### Example 2: Create a script from a file
```PowerShell
New-CMScript -ScriptName "ImportScript" -ScriptFile "\\abc\importedscript.ps1" -Fast
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ScriptFile**

Specify the path to a PowerShell script file (`.ps1`). The text of the file is used for the script in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptName**

Specify a name for the script to create.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptText**

Specify the text of the script to create.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMScript [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ScriptFile <String> -ScriptName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMScript [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ScriptName <String> -ScriptText <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
