Remove-CMDriverFromDriverPackage
--------------------------------




### Synopsis
Removes a driver from a driver package.



---


### Description

The Remove-CMDriverFromDriverPackage cmdlet removes a driver from a driver package in Configuration Manager. When you remove a driver from a driver package, the device driver content is deleted from the source directory share for the driver package.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDriverToDriverPackage](Add-CMDriverToDriverPackage)



* [Get-CMDriver](Get-CMDriver)





---


### Examples
#### Example 1: Remove a driver from a driver package
```PowerShell
PS XYZ:\> Remove-CMDriverfromDriverPackage -DriverName "Adaptec Embedded SCSI HostRAID Controller" -DriverPackageName "DrvPkg01"
```
This command removes the driver named Adaptec Embedded SCSI HostRAID Controller from the boot image named DrvPkg01.


---


### Parameters
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
|`[Int32]`|true    |named   |False        |CIId<br/>Id<br/>CI_ID|



#### **DriverName**

Specifies the name of a driver.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DriverPackage**

Specifies a CMDriverPackage object. To obtain a CMDriverPackage object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






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
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackageId <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackageName <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -Driver <IResultObject> -DriverPackage <IResultObject> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackageId <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackageName <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverId <Int32> -DriverPackage <IResultObject> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackageId <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackageName <String> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriverFromDriverPackage [-DisableWildcardHandling] -DriverName <String> -DriverPackage <IResultObject> [-Force] [-ForceWildcardHandling] [-UpdateDistributionPoints <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
