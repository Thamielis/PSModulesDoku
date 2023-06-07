New-CMOperatingSystemImageUpdateSchedule
----------------------------------------




### Synopsis
Creates an operating system image update schedule.



---


### Description

The New-CMOperatingSystemImageUpdateSchedule cmdlet creates an operating system image update schedule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)



* [Clear-CMOperatingSystemImageUpdateSchedule](Clear-CMOperatingSystemImageUpdateSchedule)





---


### Examples
#### Example 1: Create an operating system image update schedule
```PowerShell
PS ABC:\> $Win10Image = Get-CMOperatingSystemImage -Name "Windows 10 Enterprise"
PS ABC:\> $Win10SU = Get-CMSoftwareUpdate -UpdateGroupName "Win10SUgroup01"
PS ABC:\> New-CMOperatingSystemImageUpdateSchedule -Name $Win10Image.Name -SoftwareUpdate $Win10SU -RunNow -ContinueOnError $True
```
The first command gets the operating system image object named Windows 10 Enterprise and stores the object in the $Win10Image variable.


The second command gets the software update object for the update group named Win10SUgroup01 and stores the object in the $Win10SU variable.


The last command creates an operating system image update schedule to update the operating system image named Windows 10 Enterprise with the update stored in $Win10SU. The update will run now, and will continue to apply the updates even if an error is encountered.


---


### Parameters
#### **ContinueOnError**

Indicates whether software updates should be applied to the image even when there is an error.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CustomSchedule**

Specifies the date and time when the software updates are applied to the operating system image.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



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

Specifies the ID of an operating system image.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specifies an operating system image object. To obtain an operating system image object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of an operating system image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RemoveSupersededUpdates**

{{ Fill RemoveSupersededUpdates Description }}






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Boolean]`|false   |named   |False        |CleanUp|



#### **RunNow**

Indicates that the update should run now.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareUpdate**

Specifies an array of software update objects. To obtain a software update object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **UpdateDistributionPoint**

Indicates whether the operating system image on distribution points is updated after the software updates are applied.






|Type       |Required|Position|PipelineInput|Aliases                                                       |
|-----------|--------|--------|-------------|--------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsWithImage<br/>UpdateDistributionPoints|



#### **Utc**

Indicates whether to use UTC time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_ImageServicingSchedule






---


### Notes




---


### Syntax
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
