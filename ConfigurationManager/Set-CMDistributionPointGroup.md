Set-CMDistributionPointGroup
----------------------------




### Synopsis
Configure distribution point groups.



---


### Description

The Set-CMDistributionPointGroup cmdlet changes the configuration settings of a distribution point group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [New-CMDistributionPointGroup](New-CMDistributionPointGroup)



* [Remove-CMDistributionPointGroup](Remove-CMDistributionPointGroup)



* [Manage distribution point groups in Configuration Manager](Manage distribution point groups in Configuration Manager)





---


### Examples
#### Example 1: Rename a distribution point group
```PowerShell
Set-CMDistributionPointGroup -Name "DpgDept01" -NewName "DPG01"
```

#### Example 2: Add a description to a distribution point group
```PowerShell
Get-CMDistributionPointGroup -Name "DPG01" | Set-CMDistributionPointGroup -Description "Core distribution points, contact JQPublic"
```



---


### Parameters
#### **Description**

Specify an optional description for the distribution point group.






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



#### **Id**

Specify the ID of a distribution point group to configure. This ID is the GroupID property of the SMS_DistributionPointGroup WMI class. The format is a GUID, for example, `{19797865-d8d9-454b-855f-cb0f099204d0}`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |GroupId|



#### **InputObject**

Specify a distribution point group object to configure. To get this object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a distribution point group to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename the distribution point group.






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
Set-CMDistributionPointGroup [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDistributionPointGroup [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDistributionPointGroup [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
