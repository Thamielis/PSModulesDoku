Remove-CMDistributionPointFromGroup
-----------------------------------




### Synopsis
Removes a Configuration Manager distribution point from a distribution point group.



---


### Description

The Remove-CMDistributionPointFromGroup cmdlet removes a Configuration Manager distribution point from a distribution point group. Distribution point groups provide a logical grouping of distribution points for content distribution.



To remove a distribution point, specify both the distribution point to remove and the distribution point group. You can specify these values by ID or name, or you can use the Get-CMDistributionPoint (Get-CMDistributionPoint.md) cmdlet or the [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup.md)cmdlet to obtain the relevant object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDistributionPointToGroup](Add-CMDistributionPointToGroup)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)





---


### Examples
#### Example 1: Remove a distribution point by using an ID
```PowerShell
PS XYZ:\> Remove-CMDistributionPointFromGroup -DistributionPointGroupId "SMS000067" -DistributionPointId "SMS000022"
```
This command removes a distribution point that has an ID of SMS000022 from a distribution point group that has the ID SMS000067.
#### Example 2: Remove a distribution point by using a name
```PowerShell
PS XYZ:\> Remove-CMDistributionPointFromGroup -DistributionPointGroupId "SMS000067" -DistributionPointName "Western office distribution point" -Force
```
This command removes a distribution point, specified by its name, from a distribution point group that has the ID SMS000067. This command uses the Force parameter, therefore, it does not prompt you before it removes the distribution point.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**

Specifies a distribution point object. To obtain a distribution point object, use the Get-CMDistributionPoint cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroup**

Specifies a distribution point group object. To obtain a distribution point group object, use the Get-CMDistributionPointGroup cmdlet.






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
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroup <IResultObject> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroupId <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPoint <IResultObject> -DistributionPointGroupName <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> -DistributionPointId <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> -DistributionPointName <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroupId <String> -DistributionPointId <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroupId <String> -DistributionPointName <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroupName <String> -DistributionPointId <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointFromGroup [-DisableWildcardHandling] -DistributionPointGroupName <String> -DistributionPointName <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
