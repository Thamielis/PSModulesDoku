Set-CMDriverBootImage
---------------------




### Synopsis
Adds a driver to a boot image or removes a driver from a boot image.



---


### Description

The Set-CMDriverBootImage cmdlet adds a driver to a boot image or removes a driver from a boot image. You can add Windows device drivers that you have imported into the Configuration Manager driver catalog to one or more boot images. You should add only mass storage device drivers and network adapter device drivers to boot images because other types of drivers are not needed and will increase the size of the boot image.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriver](Get-CMDriver)





---


### Examples
#### Example 1: Add a driver to a boot image
```PowerShell
PS XYZ:\> Set-CMDriverBootImage -SetDriveBootImageAction AddDriverToBootImage -DriverName "Adaptec Embedded SCSI HostRAID Controller" -BootImageName "Boot image (x64)"
```
This command adds the driver named Adaptec Embedded SCSI HostRAID Controller to the boot image named Boot image (x64).
#### Example 2: Remove a driver from a boot image
```PowerShell
PS XYZ:\> Set-CMDriverBootImage -SetDriveBootImageAction RemoveDriverFromBootImage -DriverName "Adaptec SCSI HostRAID Management Processor Device" -BootImageName "Boot image (x64)"
```
This command removes the driver named Adaptec SCSI HostRAID Management Processor Device from the boot image named Boot image (x64).


---


### Parameters
#### **BootImage**

Specifies a CMBootImage object. To obtain a CMBootImage object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **BootImageId**

Specifies the ID of a boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageName**

Specifies the name of a boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Driver**

Specifies a driver object. To obtain a CMDriver object, use the Get-CMDriver (Get-CMDriver.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DriverId**

Specifies the ID of a driver.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|true    |named   |False        |Id<br/>CIId<br/>CI_ID|



#### **DriverName**

Specifies the name of a driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SetDriveBootImageAction**

Specifies the boot image action. The acceptable values for this parameter are:


* AddDriverToBootImage


* RemoveDriverFromBootImage



Valid Values:

* AddDriverToBootImage
* RemoveDriverFromBootImage






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[SetDriveBootImageActionType]`|true    |named   |False        |



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
Set-CMDriverBootImage -BootImage <IResultObject> [-DisableWildcardHandling] -DriverId <Int32> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImage <IResultObject> [-DisableWildcardHandling] -DriverName <String> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImage <IResultObject> [-DisableWildcardHandling] -Driver <IResultObject> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageId <String> [-DisableWildcardHandling] -DriverId <Int32> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageId <String> [-DisableWildcardHandling] -DriverName <String> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageId <String> [-DisableWildcardHandling] -Driver <IResultObject> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageName <String> [-DisableWildcardHandling] -DriverId <Int32> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageName <String> [-DisableWildcardHandling] -DriverName <String> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDriverBootImage -BootImageName <String> [-DisableWildcardHandling] -Driver <IResultObject> [-ForceWildcardHandling] [-PassThru] -SetDriveBootImageAction {AddDriverToBootImage | RemoveDriverFromBootImage} [-Confirm] [-WhatIf] [<CommonParameters>]
```
