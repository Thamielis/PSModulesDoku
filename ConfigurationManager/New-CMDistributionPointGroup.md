New-CMDistributionPointGroup
----------------------------




### Synopsis
Creates a distribution point group.



---


### Description

The New-CMDistributionPointGroup cmdlet creates a distribution point group. Distribution point groups provide a logical grouping of distribution points for content distribution.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Set-CMDistributionPointGroup](Set-CMDistributionPointGroup)



* [Remove-CMDistributionPointGroup](Remove-CMDistributionPointGroup)





---


### Examples
#### Example 1: Create a distribution point group
```PowerShell
PS XYZ:\> New-CMDistributionPointGroup -Name "DpgDept01" -Description "Western region"
```
This command creates a distribution point group named DpgDept01 and adds a description for the distribution point group.


---


### Parameters
#### **Description**

Specifies a description for the distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **Name**

Specifies a name of the distribution point group.






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
* IResultObject#SMS_DistributionPointGroup






---


### Notes




---


### Syntax
```PowerShell
New-CMDistributionPointGroup [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
