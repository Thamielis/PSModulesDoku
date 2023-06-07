Remove-CMPackageDeployment
--------------------------




### Synopsis
Removes a package deployment from Configuration Manager.



---


### Description

The Remove-CMPackageDeployment cmdlet remove a package deployment from Configuration Manager. A deployment includes a collection of devices or users, a package to deploy, and either a device program name or a standard program name. To specify which deployment to modify, specify the collection name, package, and program name. You can specify the package by name or ID, or you can use the Get-CMPackage (Get-CMPackage.md)cmdlet to get a package object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMPackageDeployment](New-CMPackageDeployment)



* [Get-CMPackageDeployment](Get-CMPackageDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Set-CMPackageDeployment](Set-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **Collection**

Specifies the user collection.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of a device or user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies the name of a user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specifies the ID of a package deployment.






|Type      |Required|Position|PipelineInput|Aliases                                |
|----------|--------|--------|-------------|---------------------------------------|
|`[String]`|false   |named   |False        |AdvertisementID<br/>PackageDeploymentID|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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

Specifies a package deployment object.






|Type             |Required|Position|PipelineInput |Aliases                                        |
|-----------------|--------|--------|--------------|-----------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Advertisement<br/>PackageDeployment<br/>Package|



#### **Name**

Specifies the name of a package deployment.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |PackageName|



#### **PackageId**

Specifies the ID of a package.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Id     |



#### **ProgramName**

Specifies the name of a program.






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
Remove-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-ProgramName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-ProgramName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Name <String>] [-ProgramName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-PackageId <String>] [-ProgramName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
