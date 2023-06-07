New-CMOperatingSystemInstaller
------------------------------




### Synopsis
Create an OS upgrade package.



---


### Description

Use this cmdlet to add an OS upgrade package to a Configuration Manager site. An OS upgrade package in Configuration Manager contains the Windows setup source files to upgrade an existing OS on a computer. For more information, see Manage OS upgrade packages with Configuration Manager (/mem/configmgr/osd/get-started/manage-operating-system-upgrade-packages).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Remove-CMOperatingSystemInstaller](Remove-CMOperatingSystemInstaller)



* [Set-CMOperatingSystemInstaller](Set-CMOperatingSystemInstaller)



* [Get-CMOperatingSystemUpgradeUpdateSchedule](Get-CMOperatingSystemUpgradeUpdateSchedule)



* [Manage OS images with Configuration Manager](Manage OS images with Configuration Manager)





---


### Examples
#### Example 1: Add an OS upgrade package
```PowerShell
New-CMOperatingSystemInstaller -Name "Windows 10 latest" -Path "\\Contoso01\CM\Win10latest"
```



---


### Parameters
#### **Description**

Specify an optional description to help you identify the upgrade package. The maximum length is 127 characters.






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

When you add this parameter, the site extracts a single index image from a multi-index image. It then places the new image in the same source folder as the original image in the upgrade package source files.


Using this option results in a smaller image file, and faster offline servicing. It also supports the process to Optimize image servicing (/mem/configmgr/osd/get-started/manage-operating-system-images#bkmk_resetbase), for a smaller image file after applying software updates.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|false   |named   |False        |ImageIndex|



#### **Name**

Specify the name of the OS upgrade package. The maximum length is 50 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Path**

Specify the network path to the OS upgrade package source files. The installation source files contain setup.exe and other files and folders to install the OS.






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
* IResultObject#SMS_OperatingSystemInstallPackage






---


### Notes
For more information on this return object and its properties, see SMS_OperatingSystemInstallPackage server WMI class (/mem/configmgr/develop/reference/osd/sms_operatingsysteminstallpackage-server-wmi-class).



---


### Syntax
```PowerShell
New-CMOperatingSystemInstaller [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Index <Int32>] [-Name <String>] -Path <String> [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
