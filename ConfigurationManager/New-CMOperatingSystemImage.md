New-CMOperatingSystemImage
--------------------------




### Synopsis
Create an OS image.



---


### Description

Use this cmdlet to add an OS image to a Configuration Manager site. OS images are WIM files that represent a compressed collection of reference files and folders. Configuration Manager uses these images with a task sequence to deploy an OS on a computer. For more information, see Manage OS images with Configuration Manager (/mem/configmgr/osd/get-started/manage-operating-system-images).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Set-CMOperatingSystemImage](Set-CMOperatingSystemImage)



* [Remove-CMOperatingSystemImage](Remove-CMOperatingSystemImage)



* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)



* [Manage OS images with Configuration Manager](Manage OS images with Configuration Manager)





---


### Examples
#### Example 1: Create an OS image
```PowerShell
New-CMOperatingSystemImage -Name "Windows 10 latest" -Path "\\Contoso01\CM\Images\win10_latest.wim"
```



---


### Parameters
#### **Description**

Specify an optional description to help you identify the image. The maximum length is 127 characters.






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



#### **Index**

When you add this parameter, the site extracts a single index image from a multi-index image. It then places the new image in the same source folder as the original image.


Using this option results in a smaller image file, and faster offline servicing. It also supports the process to Optimize image servicing (/mem/configmgr/osd/get-started/manage-operating-system-images#bkmk_resetbase), for a smaller image file after applying software updates.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|false   |named   |False        |ImageIndex|



#### **Name**

Specify the name of the OS image. The maximum length is 50 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specify the network path to the OS image WIM file. The path needs to include the WIM file name with the `.wim` extension.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |PackageSourcePath|



#### **Version**

Specify an optional version of the OS image. This value is for your internal versioning, not the version of the OS. The maximum length is 32 characters.






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
None





---


### Outputs
* IResultObject#SMS_ImagePackage






---


### Notes
For more information on this return object and its properties, see SMS_ImagePackage server WMI class (/mem/configmgr/develop/reference/osd/sms_imagepackage-server-wmi-class).



---


### Syntax
```PowerShell
New-CMOperatingSystemImage [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Index <Int32>] -Name <String> -Path <String> [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
