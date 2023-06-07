Remove-CMSoftwareUpdateFromGroup
--------------------------------




### Synopsis
Removes a software update from group.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareUpdate**








|Type               |Required|Position|PipelineInput |Aliases        |
|-------------------|--------|--------|--------------|---------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|SoftwareUpdates|



#### **SoftwareUpdateGroup**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroupId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**








|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|true    |named   |False        |SoftwareUpdateIds|



#### **SoftwareUpdateName**








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
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroupId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroupName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdate <IResultObject[]> -SoftwareUpdateGroup <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroup <IResultObject> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupId <String> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> -SoftwareUpdateId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateGroupName <String> -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
