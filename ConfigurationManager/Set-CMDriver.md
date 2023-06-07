Set-CMDriver
------------




### Synopsis
Changes the settings of a device driver.



---


### Description

The Set-CMDriver cmdlet changes settings of a device driver in the driver catalog.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMDriver](Disable-CMDriver)



* [Enable-CMDriver](Enable-CMDriver)



* [Get-CMDriver](Get-CMDriver)



* [Import-CMDriver](Import-CMDriver)



* [Remove-CMDriver](Remove-CMDriver)



* [Get-CMCategory](Get-CMCategory)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)





---


### Examples
#### Example 1: Modify a driver
```PowerShell
PS XYZ:\> $Driver = Get-CMDriver -Name "cdrom.sys"
PS XYZ:\> Set-CMDriver -InputObject $Driver -NewName "testDriver" -Description "Test configuration" -EnableAndAllowInstall $True -RunOnAnyPlatform $True
```
The first command gets a device driver named cdrom.sys by using the Get-CMDriver (Get-CMDriver.md)cmdlet. The command stores that object in the $Driver variable.


The second command renames the driver and adds a description. The command specifies values for the EnableAndAllowInstall and RunOnAnyPlatform parameters.
#### Example 2: Modify a driver by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDriver -Name "cdrom.sys" | Set-CMDriver -NewName testDriver -Description description -EnableAndAllowInstall $True -RunOnAnyPlatform $True
```
This command gets a driver named cdrom.sys, and then passes it to the current cmdlet by using the pipeline operator. The current cmdlet renames the driver and adds a description. The command specifies values for EnableAndAllowInstall and RunOnAnyPlatform .


---


### Parameters
#### **AddAdministrativeCategory**

Specifies an array of administrative category objects that this cmdlet adds to a driver. To obtain an administrative category object, use the Get-CMCategory (Get-CMCategory.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                    |
|-------------------|--------|--------|-------------|---------------------------|
|`[IResultObject[]]`|false   |named   |False        |AddAdministrativeCategories|



#### **AddBootImagePackage**

Specifies an array of boot image objects. Use this parameter to specify the boot images that can install the device drivers. To obtain a boot image object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **AddDriverPackage**

Specifies an array of driver package objects. Use this parameter to specify the driver packages that Configuration Manager uses to distribute the device drivers. To obtain a driver package object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **AddSupportedPlatformName**

{{ Fill AddSupportedPlatformName Description }}






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|false   |named   |False        |AddSupportedPlatformNames|



#### **AdministrativeCategory**

Specifies an array of administrative categories. Assign the device drivers to an administrative category for filtering purposes, such as Desktops or Notebooks categories.


To obtain an administrative category object, use the Get-CMCategory cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **ClearAdministrativeCategory**

Indicates that this cmdlet removes all the administrative category objects from the driver.






|Type      |Required|Position|PipelineInput|Aliases                      |
|----------|--------|--------|-------------|-----------------------------|
|`[Switch]`|false   |named   |False        |ClearAdministrativeCategories|



#### **ClearSupportedPlatformName**

{{ Fill ClearSupportedPlatformName Description }}






|Type      |Required|Position|PipelineInput|Aliases                    |
|----------|--------|--------|-------------|---------------------------|
|`[Switch]`|false   |named   |False        |ClearSupportedPlatformNames|



#### **Description**

Specifies a description for the device driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverSource**

Specifies the driver package source location. When you create a driver package, the source location of the package must point to an empty network share that is not used by another driver package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **EnableAndAllowInstall**

Indicates whether Configuration Manager enables the drivers and allows computers to install the drivers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of a device driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies a driver object. To obtain a driver object, use the Get-CMDriver cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a device driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specifies a new name for the device driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object that represents the driver. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveAdministrativeCategory**

Specifies an array of administrative category objects that this cmdlet removes from a driver. To obtain an administrative category object, use Get-CMCategory .






|Type               |Required|Position|PipelineInput|Aliases                       |
|-------------------|--------|--------|-------------|------------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveAdministrativeCategories|



#### **RemoveBootImagePackage**

Specifies an array of boot image objects. Use this parameter to remove the boot images that can install the device driver. To obtain a boot image object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **RemoveDriverPackage**

Specifies an array of driver package objects. Use this parameter to remove the driver packages that Configuration Manager uses to distribute the device drivers. To obtain a driver package object, use the Get-CMDriverPackage cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **RemoveSupportedPlatformName**

{{ Fill RemoveSupportedPlatformName Description }}






|Type        |Required|Position|PipelineInput|Aliases                     |
|------------|--------|--------|-------------|----------------------------|
|`[String[]]`|false   |named   |False        |RemoveSupportedPlatformNames|



#### **RunOnAnyPlatform**

Indicates that the device driver can run on all platforms.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SupportedPlatformName**

Specifies an array of names of platforms on which the device driver can run.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **UpdateBootImageDistributionPoint**

Indicates whether Configuration Manager updates boot images on their distribution points to add the new drivers.






|Type       |Required|Position|PipelineInput|Aliases                                                                          |
|-----------|--------|--------|-------------|---------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsForBootImagePackage<br/>UpdateBootImageDistributionPoints|



#### **UpdateDriverDistributionPoint**

Indicates that Configuration Manager updates distribution points when the device driver is added to the driver package.






|Type       |Required|Position|PipelineInput|Aliases                                                                    |
|-----------|--------|--------|-------------|---------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsForDriverPackage<br/>UpdateDriverDistributionPoints|



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
Set-CMDriver [-AddAdministrativeCategory <IResultObject[]>] [-AddBootImagePackage <IResultObject[]>] [-AddDriverPackage <IResultObject[]>] [-AddSupportedPlatformName <String[]>] [-AdministrativeCategory <IResultObject[]>] [-ClearAdministrativeCategory] [-ClearSupportedPlatformName] [-Description <String>] [-DisableWildcardHandling] [-DriverSource <String>] [-EnableAndAllowInstall <Boolean>] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-RemoveAdministrativeCategory <IResultObject[]>] [-RemoveBootImagePackage <IResultObject[]>] [-RemoveDriverPackage <IResultObject[]>] [-RemoveSupportedPlatformName <String[]>] [-RunOnAnyPlatform] [-SupportedPlatformName <String[]>] [-UpdateBootImageDistributionPoint <Boolean>] [-UpdateDriverDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriver [-AddAdministrativeCategory <IResultObject[]>] [-AddBootImagePackage <IResultObject[]>] [-AddDriverPackage <IResultObject[]>] [-AddSupportedPlatformName <String[]>] [-AdministrativeCategory <IResultObject[]>] [-ClearAdministrativeCategory] [-ClearSupportedPlatformName] [-Description <String>] [-DisableWildcardHandling] [-DriverSource <String>] [-EnableAndAllowInstall <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveAdministrativeCategory <IResultObject[]>] [-RemoveBootImagePackage <IResultObject[]>] [-RemoveDriverPackage <IResultObject[]>] [-RemoveSupportedPlatformName <String[]>] [-RunOnAnyPlatform] [-SupportedPlatformName <String[]>] [-UpdateBootImageDistributionPoint <Boolean>] [-UpdateDriverDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriver [-AddAdministrativeCategory <IResultObject[]>] [-AddBootImagePackage <IResultObject[]>] [-AddDriverPackage <IResultObject[]>] [-AddSupportedPlatformName <String[]>] [-AdministrativeCategory <IResultObject[]>] [-ClearAdministrativeCategory] [-ClearSupportedPlatformName] [-Description <String>] [-DisableWildcardHandling] [-DriverSource <String>] [-EnableAndAllowInstall <Boolean>] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-RemoveAdministrativeCategory <IResultObject[]>] [-RemoveBootImagePackage <IResultObject[]>] [-RemoveDriverPackage <IResultObject[]>] [-RemoveSupportedPlatformName <String[]>] [-RunOnAnyPlatform] [-SupportedPlatformName <String[]>] [-UpdateBootImageDistributionPoint <Boolean>] [-UpdateDriverDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
