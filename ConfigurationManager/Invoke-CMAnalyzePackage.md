Invoke-CMAnalyzePackage
-----------------------




### Synopsis
Analyze a package to convert to an application.



---


### Description

Use this cmdlet to analyze a package to convert to an application. This cmdlet invokes the package conversion manager tools that are integrated with Configuration Manager. For more information, see Package Conversion Manager (/mem/configmgr/apps/pcm/package-conversion-manager).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Invoke-CMConvertPackage](Invoke-CMConvertPackage)



* [Get-CMPackage](Get-CMPackage)



* [Package Conversion Manager](Package Conversion Manager)





---


### Examples
#### Example 1
```PowerShell
Invoke-CMAnalyzePackage -Name $packageName
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify a package ID to analyze. For example, `XYZ006C5`.






|Type        |Required|Position|PipelineInput|Aliases                         |
|------------|--------|--------|-------------|--------------------------------|
|`[String[]]`|true    |named   |False        |IDs<br/>PackageID<br/>PackageIDs|



#### **InputObject**

Applies to version 2010 and later. Specify a package object to analyze. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.


This parameter replaces the previous Package parameter.






|Type               |Required|Position|PipelineInput |Aliases             |
|-------------------|--------|--------|--------------|--------------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|Packages<br/>Package|



#### **Name**

Specify a package name to analyze.






|Type        |Required|Position|PipelineInput|Aliases                               |
|------------|--------|--------|-------------|--------------------------------------|
|`[String[]]`|false   |named   |False        |Names<br/>PackageName<br/>PackageNames|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
Starting in version 2010, the Package parameter was removed from this cmdlet. Pipe the package object, or use the InputObject parameter.



---


### Syntax
```PowerShell
Invoke-CMAnalyzePackage [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMAnalyzePackage [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMAnalyzePackage [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
