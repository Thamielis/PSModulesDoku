Set-CMAccessAccount
-------------------




### Synopsis
Modifies the properties of an access account.



---


### Description

The Set-CMAccessAccount cmdlet modifies the properties of an access account. You can add users or groups to the access account and change the level of permissions to objects to which they have permissions.



An access account is a list of users or groups that can access an established service or application that is located on a distribution point. For example, members in the Software Update Point Connection Access Account can access two services to manage software updates: Windows Server Update Services (WSUS) and WSUS Synchronization Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAccessAccount](Get-CMAccessAccount)



* [New-CMAccessAccount](New-CMAccessAccount)



* [Remove-CMAccessAccount](Remove-CMAccessAccount)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)





---


### Examples
#### Example 1: Change access to a package by using the package name
```PowerShell
PS XYZ:\> $Name = Get-CMAccessAccount -PackageName "Configuration Manager Client Package"
PS XYZ:\> Set-CMAccessAccount -PackageName $Name -Type User -UserName "CONTOSO\PFuller" -Access Read -Confirm
```
The first command gets the package name, and then stores it in the $Name variable.


The second command sets access permissions for the user to the package to Read. You must confirm the action before the command performs it.


---


### Parameters
#### **Access**

Specifies the access rights that are associated with an access account. Valid values are: No Access, Read, Change, and Full Control.



Valid Values:

* NoAccess
* Read
* Change
* FullControl






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[AccessRight]`|true    |named   |False        |



#### **AccountType**

Specifies an account type. Valid values are: Guest, User, WindowsGroup, and WindowsUser.



Valid Values:

* User
* Guest
* Administrator
* WindowsUser
* WindowsGroup






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[AccessAccountType]`|true    |named   |False        |



#### **ApplicationId**

Specifies the ID of an application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ApplicationName**

Specifies the name of an application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specifies the name of an operating system installer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageId**

Specifies the ID of a deployed software script or program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specifies the name of a deployed software script or program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SoftwareUpdateDeploymentPackageId**

Specifies the ID of a deployed software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateDeploymentPackageName**

Specifies the name of a deployed software update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserName**

Specifies a Windows user account name in domain\user format.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -ApplicationId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -ApplicationName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -BootImageId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -BootImageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] -DriverPackageId <String> [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] -DriverPackageName <String> [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount [-InputObject] <IResultObject> -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageId <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageName <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerId <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerName <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-PassThru] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -SoftwareUpdateDeploymentPackageId <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccessAccount -Access {NoAccess | Read | Change | FullControl} -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -SoftwareUpdateDeploymentPackageName <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
