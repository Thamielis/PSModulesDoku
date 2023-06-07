Export-CMDriverPackage
----------------------




### Synopsis
Export a driver package.



---


### Description

Use this cmdlet to export driver packages. You can use the Import-CMDriverPackage (Import-CMDriverPackage.md)cmdlet to import a driver package to the site.



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 6337796 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7. > > Starting in version 2103, if you try to use this cmdlet in a PowerShell version 7 session, it fails with the following error: `This cmdlet only supports the ".NET Framework" runtime.`



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Import-CMDriverPackage](Import-CMDriverPackage)



* [New-CMDriverPackage](New-CMDriverPackage)



* [Remove-CMDriverPackage](Remove-CMDriverPackage)



* [Set-CMDriverPackage](Set-CMDriverPackage)





---


### Examples
#### Example 1: Export a driver package
```PowerShell
Export-CMDriverPackage -Name "DrvPkg01" -ExportFilePath "\\Contoso02\DriverPackages\DriverPackage01.zip"
```



---


### Parameters
#### **Comment**

Specify an optional administrator comment. This comment displays in the Import Driver Package Wizard.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExportFilePath**

Specify the network path for the driver package. The path needs to specify the file, including the `.zip` extension.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>Path|



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the driver package ID to export. This value is the standard package ID, for example `XYZ00123`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specify a driver package object to export. To get this object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a driver package to export.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WithContent**

Set this parameter to $true to export all content for the driver package and drivers.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Boolean]`|false   |named   |False        |ExportAllContent|



#### **WithDependence**

Set this parameter to $true to export all associated drivers.






|Type       |Required|Position|PipelineInput|Aliases               |
|-----------|--------|--------|-------------|----------------------|
|`[Boolean]`|false   |named   |False        |ExportAssociateDrivers|



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
Export-CMDriverPackage [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -Id <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMDriverPackage [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMDriverPackage [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -Name <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
