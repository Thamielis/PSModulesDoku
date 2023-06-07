Remove-CMAlert
--------------




### Synopsis
Removes Configuration Manager alerts.



---


### Description

The Remove-CMAlert cmdlet removes one or more Configuration Manager alerts.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMAlert](Enable-CMAlert)



* [Get-CMAlert](Get-CMAlert)



* [Set-CMAlert](Set-CMAlert)



* [Suspend-CMAlert](Suspend-CMAlert)



* [Disable-CMAlert](Disable-CMAlert)





---


### Examples
#### Example 1: Remove an alert by using alert ID
```PowerShell
PS XYZ:\> Remove-CMAlert -Id "16777223"
```
This command removes an alert that has the ID 16777223.
#### Example 2: Remove an alert by using alert object variable
```PowerShell
PS XYZ:\> $AlertObj = Get-CMAlert -Id "16777221"
PS XYZ:\> Remove-CMAlert -InputObject $AlertObj
```
The first command gets a CMAlert object that has the ID 16777221, and then stores it in the $AlertObj variable.


The second command removes the alert stored in the $AlertObj variable.


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



#### **Id**

Specifies an alert ID. You can obtain the ID of an alert by using the Get-CMAlert (Get-CMAlert.md)cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies a CMAlert object. To obtain a CMAlert object, use Get-CMAlert .






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Alert  |



#### **Name**

Specifies an alert name. You can obtain the name of an alert by using Get-CMAlert .






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMAlert [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAlert [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAlert [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
