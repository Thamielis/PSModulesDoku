Set-CMScript
------------




### Synopsis
Edit a PowerShell script in Configuration Manager.



---


### Description

Use this cmdlet to edit an existing PowerShell script in Configuration Manager. These scripts are integrated and managed in Configuration Manager.



For more information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMScript](Approve-CMScript)



* [Deny-CMScript](Deny-CMScript)



* [Get-CMScript](Get-CMScript)



* [Invoke-CMScript](Invoke-CMScript)



* [New-CMScript](New-CMScript)



* [Remove-CMScript](Remove-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Change the script from a new imported file
```PowerShell
Get-CMScript -ScriptName "myScript" -Fast | Set-CMScript -ScriptFile "\\server\share\script.ps1"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a script object to modify. To get this object, use the Get-CMScript (Get-CMScript.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ScriptFile**

Specify the network path to a PowerShell script to import and use for this script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ScriptGuid**

Specify the GUID for the script to modify.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptName**

Specify the name of the script to modify.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptText**

Specify the text to use for this script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMScript [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-ScriptFile <String>] [-ScriptText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScriptFile <String>] -ScriptGuid <String> [-ScriptText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScriptFile <String>] -ScriptName <String> [-ScriptText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
