New-CMBootImage
---------------




### Synopsis
Create a custom boot image.



---


### Description

Use this cmdlet to create a custom Windows Preinstallation Environment (Windows PE) OS boot image. By default, Configuration Manager includes two boot images for x86 and x64 architectures. For more information, see Manage boot images with Configuration Manager (/mem/configmgr/osd/get-started/manage-boot-images).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBootImage](Get-CMBootImage)



* [Remove-CMBootImage](Remove-CMBootImage)



* [Set-CMBootImage](Set-CMBootImage)



* [Manage boot images with Configuration Manager](Manage boot images with Configuration Manager)





---


### Examples
#### Example 1: Create a custom boot image
```PowerShell
New-CMBootImage -Path "\\Server99.Contoso.com\SMS_CCC\osd\boot\x64\boot.wim" -Index 1 -Name "Custom boot image" -Version "11" -Description "WinPE Boot Image x64 Approved 9/1/2012"
```



---


### Parameters
#### **Description**

Specify an optional description of a boot image to help you identify it.






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

Specify the index of the image in the WinPE file to use for this boot image.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|true    |named   |False        |ImageIndex|



#### **Name**

Specify the name of the boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specify the network path of the original WIM file for the boot image.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |ImagePath|



#### **Version**

Specify the version of the boot image. This value isn't the OS version, but a string that you manage.






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
* IResultObject#SMS_BootImagePackage






---


### Notes
For more information on this return object and its properties, see SMS_BootImagePackage server WMI class (/mem/configmgr/develop/reference/osd/sms_bootimagepackage-server-wmi-class).



---


### Syntax
```PowerShell
New-CMBootImage [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Index <Int32> -Name <String> -Path <String> [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
