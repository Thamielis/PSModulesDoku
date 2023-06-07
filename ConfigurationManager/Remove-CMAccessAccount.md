Remove-CMAccessAccount
----------------------




### Synopsis
Removes users or groups from an access account.



---


### Description

The Remove-CMAccessAccount cmdlet removes users or groups from an access account.



An access account is a list of users or groups that can access an established service or application that is located on a distribution point. For example, members in the Software Update Point Connection Access Account can access two services to manage software updates: Windows Server Update Services (WSUS) and WSUS Synchronization Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAccessAccount](New-CMAccessAccount)



* [Get-CMAccessAccount](Get-CMAccessAccount)



* [Set-CMAccessAccount](Set-CMAccessAccount)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)





---


### Examples
#### Example 1: Remove a user from an access account for an application by using its name
```PowerShell
PS XYZ:\> Remove-CMAccessAccount -ApplicationName "SharePoint 2010" -Type WindowsUser -UserName "CONTOSO\ENarvaez" -Confirm
```
This command removes a Windows user from the access account for an application that is specified by using its name. You must confirm the action before the command performs it.
#### Example 2: Remove a group from an access account for a package by using its ID
```PowerShell
PS XYZ:\> $ID = Get-CMAccessAccount -PackageId "CM1100002"
PS XYZ:\> Remove-CMAccessAccount -PackageId $ID -Type WindowsGroup -UserName "CONTOSO\Guest"
```
The first command gets the package object ID, and then stores it in the variable $ID.


The second command removes a group from the access account for the specified package. No confirmation is required.


---


### Parameters
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
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -ApplicationId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -ApplicationName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -BootImageId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} -BootImageName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] -DriverPackageId <String> [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] -DriverPackageName <String> [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount [-InputObject] <IResultObject> -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -OperatingSystemImageId <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -OperatingSystemImageName <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -OperatingSystemInstallerId <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -OperatingSystemInstallerName <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -PackageId <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -PackageName <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageId <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAccessAccount -AccountType {User | Guest | Administrator | WindowsUser | WindowsGroup} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageName <String> [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
