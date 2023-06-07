Add-CMDistributionPointToGroup
------------------------------




### Synopsis
Adds a distribution point to a distribution point group.



---


### Description

The Add-CMDistributionPointToGroup cmdlet adds a distribution point to a distribution point group. Distribution point groups provide a logical grouping of distribution points for content distribution.



You can add one or more distribution points from any site in the Configuration Manager hierarchy to the distribution point group. You can also add the distribution point to more than one distribution point group so that you can manage and monitor content from a central location for distribution points that span multiple sites.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMDistributionPointFromGroup](Remove-CMDistributionPointFromGroup)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)





---


### Examples
#### Example 1: Add a distribution point to a group
```PowerShell
PS XYZ:\>Add-CMDistributionPointToGroup -DistributionPointGroupName "DPG01" -Id "{FA921CF2-89C9-407D-A21D-FE6947F2C00A}"
```
This command adds the distribution point that has the Id FA921CF2-89C9-407D-A21D-FE6947F2C00A to the distribution point group named DPG01.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**

Specifies a distribution point object. To obtain a CMDistributionPoint object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroup**

Specifies a distribution point group object. To obtain a CMDistributionPointGroup object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroupId**

Specifies the ID of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointGroupName**

Specifies the name of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointId**

Specifies the ID of a distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointName**

Specifies the name of a distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroup <IResultObject> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroupId <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroupName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> -DistributionPointId <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> -DistributionPointName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroupId <String> -DistributionPointId <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroupId <String> -DistributionPointName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroupName <String> -DistributionPointId <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPointToGroup [-DisableWildcardHandling] -DistributionPointGroupName <String> -DistributionPointName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
