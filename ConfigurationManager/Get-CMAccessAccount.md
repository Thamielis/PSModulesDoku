Get-CMAccessAccount
-------------------




### Synopsis
Gets an access account.



---


### Description

The Get-CMAccessAccount cmdlet gets an access account.



An access account is a list of users or groups that can access an established service or application that is located on a distribution point. For example, members in the Software Update Point Connection access account can access two services to manage software updates: Windows Server Update Services (WSUS) and WSUS Synchronization Manager. You can get an access account to change the network access permissions for clients who use the account.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAccessAccount](New-CMAccessAccount)



* [Set-CMAccessAccount](Set-CMAccessAccount)



* [Remove-CMAccessAccount](Remove-CMAccessAccount)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)





---


### Examples
#### Example 1: Get an access account for a package by using the package ID
```PowerShell
PS XYZ:\> $ID = Get-CMPackage -PackageName "Configuration Manager Client Package"
PS XYZ:\> Get-CMAccessAcccount -PackageId $ID
Name:          Administrator
Type:          Administrator
Access:        FullControl
Sitecode:      CM1
PackageID:     CM100002
Name:          CONTOSO\PFuller
Type:          WindowsUser
Access:        Read
Sitecode:      CM1
PackageID:     CM100002
```
The first command gets the package that is identified by name. The command stores the ID of the specified package in the $ID variable.


The second command gets the access account for the identified package. The command output describes all users and groups that can access this package.
#### Example 2: Get an access account for a boot image by using the boot image name
```PowerShell
PS XYZ:\> Get-CMAccessAccount -BootImageName "System Image (x64)"
Name:          CONTOSO\EDaugherty
Type:          WindowsUser
Access:        Read
Sitecode:      CM1
Boot Image:    System Image (x64)
```
The command gets the access account for a system boot image that is specified by using its name.


---


### Parameters
#### **ApplicationId**

Specifies the ID of an application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ApplicationName**

Specifies the name of an application object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageId**

Specifies the ID of a boot image object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageName**

Specifies the name of a boot image object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                                                                                                                          |
|-----------------|--------|--------|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|DriverPackage<br/>Application<br/>OperatingSystemImage<br/>OperatingSystemInstaller<br/>Package<br/>SoftwareUpdateDeploymentPackage<br/>BootImage|



#### **OperatingSystemImageId**

Specifies the ID of an operating system image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemImageName**

Specifies the name of an operating system image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemInstallerId**

Specifies the ID of an operating system installer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemInstallerName**

Specifies the name of an operating system installer object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageId**

Specifies the ID of a deployed software script or program object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specifies the name of a deployed software script or program object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateDeploymentPackageId**

Specifies the ID of a software update deployment object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateDeploymentPackageName**

Specifies the name of a deployed software update object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserName**

Specifies a Windows user account name in domain\user format.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* AccessAccount[]


* AccessAccount






---


### Notes




---


### Syntax
```PowerShell
Get-CMAccessAccount -ApplicationId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount -ApplicationName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount -BootImageId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount -BootImageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] -DriverPackageId <String> [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] -DriverPackageName <String> [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageId <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageName <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerId <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerName <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageId <String> [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMAccessAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageName <String> [-UserName <String>] [<CommonParameters>]
```
