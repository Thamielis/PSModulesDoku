Clear-CMOperatingSystemImageUpdateSchedule
------------------------------------------




### Synopsis
Removes a schedule for updating an operating system image.



---


### Description

The Clear-CMOperatingSystemImageUpdateSchedule cmdlet removes a schedule for updating an operating system image from a Configuration Manager site.



Operating system images are .wim format files, which represent a compressed collection of reference files and folders that Configuration Manager requires to successfully install and configure an operating system on a computer. You can use Configuration Manager to define a schedule for updating these images by using Component Based Servicing (CBS), then delete unwanted schedules by using this cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)





---


### Examples
#### Example 1: Remove a schedule for updating an operating system image by using a name
```PowerShell
PS XYZ:\>Clear-CMOperatingSystemUpdateSchedule -OperatingSystemImageName "Win8UpdateSchedule"
```
This command removes a schedule named Win8UpdateSchedule that updates an operating system image.
#### Example 2: Remove a schedule for updating an operating system image by using an object
```PowerShell
PS XYZ:\> $Win8UpdateSchedule = Get-CMOperatingSystemUpdateSchedule -Id 1207
PS XYZ:\> Clear-CMOperatingSystemImageUpdateSchedule -OperatingSystemImageName "Win8UpdateSchedule"
```
The first command gets the image update schedule by using the ID 1207. The command stores this schedule in the $UpdateSchedObject variable.


The second command removes the image update schedule by using $UpdateSchedObject.


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








|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |named   |False        |OperatingSystemImageId|



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                   |
|-----------------|--------|--------|--------------|------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|OperatingSystemImage<br/>ServicingSchedule|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|true    |named   |False        |OperatingSystemImageName|



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
Clear-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMOperatingSystemImageUpdateSchedule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
