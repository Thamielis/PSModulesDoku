Add-CMSoftwareUpdateToGroup
---------------------------




### Synopsis
Adds a software update to a software update group in Configuration Manager.



---


### Description

The Add-CMSoftwareUpdateToGroup cmdlet adds a software update to a software update group in Configuration Manager. You can specify a software update by name or by ID or use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet to obtain an update. Likewise, you can specify a software update group by name or by ID or use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet to obtain one.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)





---


### Examples
#### Example 1: Add an update to a software group
```PowerShell
PS XYZ:\>Add-CMSoftwareUpdateToGroup -SoftwareUpdateGroupName "Accounting Group updates" -SoftwareUpdateId "SMS00078"
```
This command adds a software update with the ID SMS00078 to the update group named Accounting Group updates.
#### Example 2: Add an update to a software group by using IDs
```PowerShell
PS XYZ:\>Add-CMSoftwareUpdateToGroup -SoftwareUpdateGroupId "SUP00045" -SoftwareUpdateId "SMS00078"
```
This command adds a software update that has the ID SMS00078 to the update group with the specified ID.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareUpdate**

Specifies a software update object. To obtain a software update object, use Get-CMSoftwareUpdate .






|Type               |Required|Position|PipelineInput |Aliases        |
|-------------------|--------|--------|--------------|---------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|SoftwareUpdates|



#### **SoftwareUpdateGroup**

Specifies a software update group object. To obtain a software update group object, use Get-CMSoftwareUpdateGroup .






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroupId**

Specifies an ID of a software group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specifies a name of a software group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specifies an ID of a software update.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|true    |named   |False        |SoftwareUpdateIds|



#### **SoftwareUpdateName**

Specifies a name of a software update.






|Type        |Required|Position|PipelineInput|Aliases            |
|------------|--------|--------|-------------|-------------------|
|`[String[]]`|true    |named   |False        |SoftwareUpdateNames|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroupId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroupName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroup <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSoftwareUpdateToGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
