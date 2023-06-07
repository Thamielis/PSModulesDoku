Import-CMDriver
---------------




### Synopsis
Import a device driver into the driver catalog.



---


### Description

The Import-CMDriver cmdlet imports one or more device drivers into the driver catalog in Configuration Manager. When you import device drivers into the catalog, you can add the device drivers to driver packages or to boot image packages.



As part of the import process for the device driver, Configuration Manager reads the following information associated with the device:



- Provider



- Class



- Version



- Signature



- Supported hardware



- Supported platform






By default, the driver is named after the first hardware device that it supports. To rename the device driver, use the -NewName parameter of the Set-CMDriver (Set-CMDriver.md)cmdlet. The supported platforms list is based on the information in the INF file of the driver. Because the accuracy of this information can vary, manually verify that the device driver is supported after you import it into the driver catalog.


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Get-CMDriver](Get-CMDriver)



* [Set-CMDriver](Set-CMDriver)



* [Enable-CMDriver](Enable-CMDriver)



* [Disable-CMDriver](Disable-CMDriver)



* [Remove-CMDriver](Remove-CMDriver)



* [Get-CMCategory](Get-CMCategory)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Manage drivers in Configuration Manager](Manage drivers in Configuration Manager)





---


### Examples
#### Example 1: Import all device drivers in a path
```PowerShell
Import-CMDriver -Path "\\Server1\Driver" -ImportFolder
```

#### Example 2: Import a device driver by name
```PowerShell
Import-CMDriver -Path "\\Server1\Driver\driver.inf"
```



---


### Parameters
#### **AdministrativeCategory**

Specify an array of category objects. To get this object, use the Get-CMCategory (Get-CMCategory.md)cmdlet.


Assign the device drivers to a category for filtering purposes, such as Desktops or Notebooks.






|Type               |Required|Position|PipelineInput|Aliases                 |
|-------------------|--------|--------|-------------|------------------------|
|`[IResultObject[]]`|false   |named   |False        |AdministrativeCategories|



#### **AdministrativeCategoryName**

Instead of getting and specifying an object for a category with the AdministrativeCategory parameter, use this parameter to simply specify the name of a category. You can also use an array of category names.






|Type        |Required|Position|PipelineInput|Aliases                    |
|------------|--------|--------|-------------|---------------------------|
|`[String[]]`|false   |named   |False        |AdministrativeCategoryNames|



#### **BootImagePackage**

Specify an array of boot image objects. To get this object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.


Use this parameter to add the imported drivers to the specified boot images.


Only add drivers that Windows PE (WinPE) requires to boot:


* Make sure that the drivers that you add to the boot image match the architecture of the boot image.


* WinPE already comes with many drivers built-in. Add only network and storage drivers that aren't included in WinPE.


* Add only network and storage drivers to the boot image, unless there are requirements for other drivers in WinPE.


* It's best to use drivers that have a valid digital signature.






|Type               |Required|Position|PipelineInput|Aliases          |
|-------------------|--------|--------|-------------|-----------------|
|`[IResultObject[]]`|false   |named   |False        |BootImagePackages|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverPackage**

Specify an array of driver package objects. To get this object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.


Use this parameter to add the imported drivers to the specified driver packages.






|Type               |Required|Position|PipelineInput|Aliases       |
|-------------------|--------|--------|-------------|--------------|
|`[IResultObject[]]`|false   |named   |False        |DriverPackages|



#### **EnableAndAllowInstall**

Enable the driver and allow clients to install it during the Auto Apply Driver (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_AutoApplyDrivers)task sequence step.


Drivers added to the driver package aren't affected.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ImportDuplicateDriverOption**

Specify how Configuration Manager manages duplicate device drivers.


* `AppendCategory`: Import the driver and append a new category to the existing categories `- KeepExistingCategory`: Import the driver and keep the existing categories - `NotImport`: Don't import the driver


* `OverwriteCategory`: Import the driver and overwrite the existing categories



Valid Values:

* NotImport
* AppendCategory
* KeepExistingCategory
* OverwriteCategory






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[ImportDuplicateDriverOption]`|false   |named   |False        |



#### **ImportFolder**

Add this parameter to import all the device drivers in the target folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specify a path to the driver files to import.






|Type      |Required|Position|PipelineInput|Aliases                                                                  |
|----------|--------|--------|-------------|-------------------------------------------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ImportFilePath<br/>Location<br/>UncFileLocation|



#### **SupportedPlatform**

Specify a supported platform object to which the device driver is applicable and can run. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |SupportedPlatforms|



#### **SupportedPlatformName**

Specifies an array of supported platforms name on which the device driver can run. For example, `"All Windows 10 (64-bit)"`.






|Type        |Required|Position|PipelineInput|Aliases               |
|------------|--------|--------|-------------|----------------------|
|`[String[]]`|false   |named   |False        |SupportedPlatformNames|



#### **UpdateBootImageDistributionPoint**

Indicates whether Configuration Manager updates boot images on their distribution points to add the new drivers.






|Type       |Required|Position|PipelineInput|Aliases                                                                          |
|-----------|--------|--------|-------------|---------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsForBootImagePackage<br/>UpdateBootImageDistributionPoints|



#### **UpdateDriverPackageDistributionPoint**

If you use the -DriverPackage parameter, set this parameter to `$true` to update the driver package on assigned distribution points.






|Type       |Required|Position|PipelineInput|Aliases                                 |
|-----------|--------|--------|-------------|----------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPointsforDriverPackage|



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
* IResultObject#SMS_Driver






---


### Notes




---


### Syntax
```PowerShell
Import-CMDriver [-AdministrativeCategory <IResultObject[]>] [-AdministrativeCategoryName <String[]>] [-BootImagePackage <IResultObject[]>] [-DisableWildcardHandling] [-DriverPackage <IResultObject[]>] [-EnableAndAllowInstall <Boolean>] [-ForceWildcardHandling] [-ImportDuplicateDriverOption {NotImport | AppendCategory | KeepExistingCategory | OverwriteCategory}] [-ImportFolder] -Path <String> [-SupportedPlatform <IResultObject[]>] [-SupportedPlatformName <String[]>] [-UpdateBootImageDistributionPoint <Boolean>] [-UpdateDriverPackageDistributionPoint <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
