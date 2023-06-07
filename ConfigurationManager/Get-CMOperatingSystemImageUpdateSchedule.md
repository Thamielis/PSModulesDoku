Get-CMOperatingSystemImageUpdateSchedule
----------------------------------------




### Synopsis
Retrieves an operating system image update schedule object in Configuration Manager.



---


### Description

The Get-CMOperatingSystemImageUpdateSchedule cmdlet retrieves an object that represents an operating system image update schedule in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Clear-CMOperatingSystemImageUpdateSchedule](Clear-CMOperatingSystemImageUpdateSchedule)





---


### Examples
#### Example 1: Retrieve the operating system image update schedule
```PowerShell
PS XYZ:\> Get-CMOperatingSystemImageUpdateSchedule -Id "1207"
```
This command retrieves the operating system image update schedule identified by the ID 1207.


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

Specifies an array of IDs of operating system image update schedules in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specifies an operating system image update schedule object in Configuration Manager.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of an operating system image update schedule in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ImageServicingSchedule


* IResultObject#SMS_ImageServicingSchedule






---


### Notes




---


### Syntax
```PowerShell
Get-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
