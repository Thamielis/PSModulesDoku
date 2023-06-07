Remove-CMPackage
----------------




### Synopsis
Removes a Configuration Manager package.



---


### Description

The Remove-CMPackage cmdlet removes a package in Configuration Manager. You can delete a package from the site where it was created. Configuration Manager cannot delete a package from a distribution point if a user has locked a network file.



When you remove a package, Configuration Manager removes it from the database. If the package was sent to child sites, Configuration Manager removes the package information at those child sites. If a compressed version of source files for the package exists, Configuration Manager deletes the compressed file from the site server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMPackage](Export-CMPackage)



* [Get-CMPackage](Get-CMPackage)



* [Import-CMPackage](Import-CMPackage)



* [New-CMPackage](New-CMPackage)



* [Set-CMPackage](Set-CMPackage)





---


### Examples
#### Example 1: Remove a package
```PowerShell
PS XYZ:\> Remove-CMPackage -Id "CM10000D"
```
This command removes the package that has the ID CM10000D.
#### Example 2: Remove a package by using an object variable
```PowerShell
PS XYZ:\> $Pkg = Get-CMPackage -Id "CM10000D"
PS XYZ:\> Remove-CMPackage -InputObject $Pkg
```
The first command gets the package that has the ID CM10000D, and then stores the results to the $Pkg variable.


The second command removes the package stored in the $Pkg variable.


---


### Parameters
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



#### **Id**

Specifies an array of package IDs.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specifies a CMPackage object. To obtain a CMPackage object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of package names.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
