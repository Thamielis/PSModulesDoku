Get-CMDistributionPointGroup
----------------------------




### Synopsis
Gets distribution point groups.



---


### Description

The Get-CMDistributionPointGroup cmdlet gets one or more distribution point groups.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDistributionPointGroup](New-CMDistributionPointGroup)



* [Remove-CMDistributionPointGroup](Remove-CMDistributionPointGroup)



* [Set-CMDistributionPointGroup](Set-CMDistributionPointGroup)





---


### Examples
#### Example 1: Get a distribution point group by using an ID
```PowerShell
PS XYZ:\> Get-CMDistributionPointGroup -Id "{6617708D-0F98-4898-8D05-9E882C23DCB2}"
```
This command get the distribution point group that has the ID 6617708D-0F98-4898-8D05-9E882C23DCB2.
#### Example 2: Get a distribution point group by using a name
```PowerShell
PS XYZ:\> Get-CMDistributionPointGroup -Name "Dpg01" -Id "{FA921CF2-89C9-407D-A21D-FE6947F2C00A}"
```
This command gets the distribution point group named Dpg01 and that has the ID FA921CF2-89C9-407D-A21D-FE6947F2C00A.


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



#### **Id**

Specifies an array of IDs of distribution point groups.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |GroupId|



#### **Name**

Specifies the name of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_DistributionPointGroup


* IResultObject#SMS_DistributionPointGroup






---


### Notes




---


### Syntax
```PowerShell
Get-CMDistributionPointGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMDistributionPointGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
