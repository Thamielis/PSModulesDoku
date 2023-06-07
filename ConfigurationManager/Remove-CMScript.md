Remove-CMScript
---------------




### Synopsis
Remove a PowerShell script from Configuration Manager.



---


### Description

Use this cmdlet to remove a PowerShell script from Configuration Manager. These scripts are integrated and managed in Configuration Manager. When you remove a script, it you can't run it anymore. Instead of removing a script, you can also deny it so it can't run on clients. For more information, see Deny-CMScript (Deny-CMScript.md).



For more general information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMScript](Approve-CMScript)



* [Deny-CMScript](Deny-CMScript)



* [Get-CMScript](Get-CMScript)



* [Invoke-CMScript](Invoke-CMScript)



* [New-CMScript](New-CMScript)



* [Set-CMScript](Set-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Remove a script by using the script name
```PowerShell
Remove-CMScript -ScriptName "getUsers" -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a script object to remove. To get this object, use the Get-CMScript (Get-CMScript.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Script |



#### **ScriptName**

Specify the name of the script to remove.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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
Remove-CMScript [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMScript [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -ScriptName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
