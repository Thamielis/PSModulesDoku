Publish-CMPrestageContent
-------------------------




### Synopsis
Publishes files to a distribution point.



---


### Description

The Publish-CMPrestageContent cmdlet publishes files for applications, images, packages, or operating system installers to a distribution point without using the Configuration Manager distribution process.



Specify the distribution site, the file name, and the item to publish.



You can specify any of the following to publish to a distribution point:



- Application



- BootImage



- DeploymentPackage



- DriverPackage



- OperatingSystemImage



- OperatingSystemInstaller



- Package






You can specify the item to be published by name or ID, or use another cmdlet to get the desired item.


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDeploymentPackage](Get-CMDeploymentPackage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1: Publish a package
```PowerShell
PS XYZ:\>Publish-CMPrestageContent -PackageId "CM200001" -DistributionPointName "FileDist02.Western.Contoso.com" -FileName "C:\Users\admin\Documents\Package.pkgx"
```
This command publishes the package that has the ID CM200001 to the specified distribution point as the specified .pkgx file.
#### Example 2: Publish a boot image
```PowerShell
PS XYZ:\>Publish-CMPrestageContent -BootImageId "CM200005" -DistributionPointName "FileDist02.Western.Contoso.com" -FileName "C:\Users\admin\Documents\BootImage.pkgx"
```
This command publishes the boot image that has the ID CM200005 to the specified distribution point as the specified .pkgx file.
#### Example 3: Publish a driver package
```PowerShell
PS XYZ:\>Publish-CMPrestageContent -DriverPackageId "CM20000F" -DistributionPointName "FileDist02.Western.Contoso.com" -FileName "C:\Users\admin\Documents\DriverPackage.pkgx"
```
This command publishes the driver package that has the ID CM20000F to the specified distribution point as the specified .pkgx file.
#### Example 4: Publish an operating system image
```PowerShell
PS XYZ:\>Publish-CMPrestageContent -OperatingSystemImageId "CM200006" -DistributionPointName "FileDist02.Western.Contoso.com" -FileName "C:\Users\admin\Documents\OSImage.pkgx"
```
This command publishes the operating system image that has the ID CM200006 to the specified distribution point as the specified .pkgx file.
#### Example 5: Publish an operating system installer
```PowerShell
PS XYZ:\>Publish-CMPrestageContent -OperatingSystemInstallerId "CM200017" -DistributionPointName "FileDist02.Western.Contoso.com" -FileName "C:\Users\admin\Documents\OSInstaller.pkgx"
```
This command publishes the operating system installer that has the ID CM200017 to the specified distribution point as the specified .pkgx file.


---


### Parameters
#### **Application**

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ApplicationId**

Specifies an array of IDs of applications.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |ApplicationIds|



#### **ApplicationName**

Specifies an array of names of applications.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|true    |named   |False        |ApplicationNames|



#### **BootImage**

Specifies a boot image object. To obtain a boot image object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **BootImageId**

Specifies an array of IDs of boot images.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |BootImageIds|



#### **BootImageName**

Specifies an array of names of boot images.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |BootImageNames|



#### **DeploymentPackage**

Specifies a deployment package object. To obtain a deployment package object, use the Get-CMDeploymentPackage (Get-CMDeploymentPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **DeploymentPackageId**

Specifies an array of IDs of deployment packages.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageIds|



#### **DeploymentPackageName**

Specifies an array of names of deployment packages.






|Type        |Required|Position|PipelineInput|Aliases               |
|------------|--------|--------|-------------|----------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageNames|



#### **Description**

Specifies a description for the content.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableDependencyExport**








|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[Switch]`|false   |named   |False        |DisableExportAllDependencies|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointName**

Specifies a distribution point for the content.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DriverPackage**

Specifies a driver package object. To obtain a driver package object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **DriverPackageId**

Specifies an array of IDs of driver packages.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|true    |named   |False        |DriverPackageIds|



#### **DriverPackageName**

Specifies an array of names of driver packages.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|true    |named   |False        |DriverPackageNames|



#### **FileName**

Specifies a file name for a .pkgx file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **OperatingSystemImage**

Specifies an operating system image object. To obtain an operating system image object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **OperatingSystemImageId**

Specifies an array of IDs of operating system images.






|Type        |Required|Position|PipelineInput|Aliases                |
|------------|--------|--------|-------------|-----------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageIds|



#### **OperatingSystemImageName**

Specifies an array of names of operating system images.






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageNames|



#### **OperatingSystemInstaller**

Specifies an operating system installer object. To obtain an operating system installer object, use the Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **OperatingSystemInstallerId**

Specifies an array of IDs of operating system installers.






|Type        |Required|Position|PipelineInput|Aliases                    |
|------------|--------|--------|-------------|---------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemInstallerIds|



#### **OperatingSystemInstallerName**

Specifies an array of names of operating system installers.






|Type        |Required|Position|PipelineInput|Aliases                      |
|------------|--------|--------|-------------|-----------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemInstallerNames|



#### **Package**

Specifies a package object. To obtain a package object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **PackageId**

Specifies an array of IDs of packages.






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|true    |named   |False        |PackageIds|



#### **PackageName**

Specifies an array of names of packages.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |PackageNames|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Publish-CMPrestageContent -Application <IResultObject> [-Description <String>] [-DisableDependencyExport] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -ApplicationId <String[]> [-Description <String>] [-DisableDependencyExport] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -ApplicationName <String[]> [-Description <String>] [-DisableDependencyExport] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -BootImage <IResultObject> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -BootImageId <String[]> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -BootImageName <String[]> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -DeploymentPackage <IResultObject> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -DeploymentPackageId <String[]> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent -DeploymentPackageName <String[]> [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -DriverPackage <IResultObject> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -DriverPackageId <String[]> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -DriverPackageName <String[]> -FileName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemImage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemImageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemImageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemInstaller <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemInstallerId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -OperatingSystemInstallerName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -Package <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -PackageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContent [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FileName <String> [-ForceWildcardHandling] -PackageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
