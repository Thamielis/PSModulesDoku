Import-CMUserDeviceAffinity
---------------------------




### Synopsis
Imports a file that contains user and device affinities to Configuration Manager.



---


### Description

The Import-CMUserDeviceAffinity cmdlet imports a file that contains user and device affinities to Configuration Manager. User device affinity in Configuration Manager is a method of associating a user with one or more specified devices.



The devices listed in the file that you specify in the FileName parameter must already exist as resources in the Configuration Manager database. If they do not exist, the import will fail.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUserDeviceAffinity](Get-CMUserDeviceAffinity)





---


### Examples
#### Example 1: Import a user device affinity
```PowerShell
PS XYZ:\>Import-CMUserDeviceAffinity -FileName "Remote_Users.csv" -EnableColumnHeadings $True
```
This command imports the user device affinity in the file named Remote_Users.csv. The EnableColumnHeadings parameter specifies that the import file has column headings for reference purposes.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableColumnHeading**








|Type       |Required|Position|PipelineInput|Aliases             |
|-----------|--------|--------|-------------|--------------------|
|`[Boolean]`|false   |named   |False        |EnableColumnHeadings|



#### **FileName**

Specifies a .csv file that contains a list of users and devices you want to create an affinity between. Each user and device pair must be on a separate line separated by a comma. Use the format <Domain>\<user name>,<device NetBIOS name>.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|true    |named   |False        |FilePath<br/>ImportFilePath<br/>Path|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MappingOrder**





Valid Values:

* Users
* Devices
* Ignored






|Type         |Required|Position|PipelineInput|Aliases      |
|-------------|--------|--------|-------------|-------------|
|`[Mapping[]]`|false   |named   |False        |MappingOrders|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Import-CMUserDeviceAffinity [-DisableWildcardHandling] [-EnableColumnHeading <Boolean>] -FileName <String> [-ForceWildcardHandling] [-MappingOrder {Users | Devices | Ignored}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
