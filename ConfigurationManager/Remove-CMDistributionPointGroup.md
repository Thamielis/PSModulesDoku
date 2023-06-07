Remove-CMDistributionPointGroup
-------------------------------




### Synopsis
Removes distribution point groups.



---


### Description

The Remove-CMDistributionPointGroup cmdlet removes one or more distribution point groups. When you remove a distribution point group, you cannot use the distribution point group to distribute content to the site collections that are associated with the distribution point group and to the distribution points that are members of the distribution point group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDistributionPointGroup](New-CMDistributionPointGroup)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Set-CMDistributionPointGroup](Set-CMDistributionPointGroup)





---


### Examples
#### Example 1: Remove a distribution point group by using an ID
```PowerShell
PS XYZ:\> Remove-CMDistributionPointGroup -Id "{03BCD6FE-5604-4725-B650-DD1EA03676DE}"
```
This command removes the distribution point group that has the ID 03BCD6FE-5604-4725-B650-DD1EA03676DE.
#### Example 2: Remove a distribution point group by using a name
```PowerShell
PS XYZ:\> Remove-CMDistributionPointGroup -Name "DpgDept01"
```
This command removes the distribution point group named DpgDept01.


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

Specifies an array of IDs of distribution point groups.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |GroupId|



#### **InputObject**

Specifies a CMDistributionPointGroup object. To obtain a CMDistributionPointGroup object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a distribution point group.






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
Remove-CMDistributionPointGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDistributionPointGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
