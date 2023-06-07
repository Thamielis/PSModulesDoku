Add-CMDriverToDriverPackage
---------------------------




### Synopsis
Adds a device driver to a Configuration Manager driver package.



---


### Description

The Add-CMDriverToDriverPackage cmdlet adds a device driver to a Configuration Manager driver package.



A driver package contains the content associated with one or more device drivers. Device drivers must to be added to a driver package and copied to a distribution point before Configuration Manager clients can install them.



You can add Windows device drivers that have been imported into the driver catalog to an existing driver package. When a device driver is added to a driver package, Configuration Manager copies the device driver content from the driver source location to the driver package.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMDriverFromDriverPackage](Remove-CMDriverFromDriverPackage)



* [Get-CMDriver](Get-CMDriver)



* [Get-CMDriverPackage](Get-CMDriverPackage)





---


### Examples
#### Example 1: Add a driver to a driver package
```PowerShell
PS XYZ:\>Add-CMDriverToDriverPackage -DriverName "Adaptec Embedded SCSI HostRAID Controller" -DriverPackageName "DrvPkg01"
```
This command adds the driver named Adaptec Embedded SCSI HostRAID Controller to the driver package named DrvPkg01.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Driver**

Specifies a driver object. To obtain a CMDriver object, use the Get-CMDriver cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DriverId**

Specifies the ID of a driver.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **DriverName**

Specifies the name of a driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DriverPackage**

Specifies a driver package object. To obtain a CMDriverPackage object, use the Get-CMDriverPackage cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DriverPackageId**

Specifies the ID of a driver package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DriverPackageName**

Specifies the name of a driver package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UpdateDistributionPoints**

{{ Fill UpdateDistributionPoints Description }}






|Type       |Required|Position|PipelineInput|Aliases                                                                                                         |
|-----------|--------|--------|-------------|----------------------------------------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |UpdateDistributionPoint<br/>UpdateDistributionPointForDriverPackage<br/>UpdateDistributionPointsForDriverPackage|



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
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackage <IResultObject> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackageId <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackageName <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackageId <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackageName <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackage <IResultObject> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackageId <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackageName <String> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDriverToDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackage <IResultObject> [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
