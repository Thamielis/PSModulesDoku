Export-CMPackage
----------------




### Synopsis
Export a legacy package.



---


### Description

Use this cmdlet to export a Configuration Manager legacy package. You can use the Import-CMPackage (Import-CMPackage.md)cmdlet to import a legacy package to another site.



Configuration Manager current branch continues to support packages and programs that were used in Configuration Manager 2007. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 6337796 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7. > > Starting in version 2103, if you try to use this cmdlet in a PowerShell version 7 session, it fails with the following error: `This cmdlet only supports the ".NET Framework" runtime.`



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Import-CMPackage](Import-CMPackage)



* [Get-CMPackage](Get-CMPackage)



* [New-CMPackage](New-CMPackage)



* [Remove-CMPackage](Remove-CMPackage)



* [Set-CMPackage](Set-CMPackage)





---


### Examples
#### Example 1: Export a package by using an ID
```PowerShell
Export-CMPackage -Id "ST120001" -FileName "\\Deploy01\ExportPackages\ST120001.zip"
```

#### Example 2: Export a package by using a variable
```PowerShell
$DeplObj = Get-CMPackage -Id "ST120001"
Export-CMPackage - "ST120001" -FileName "\\Deploy01\ExportPackages\ST120001.zip" -InputObject $DeplObj
```



---


### Parameters
#### **Comment**

Specify an optional administrator comment. This comment displays in the Import Package Wizard.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileName**

Specify the network path for the package. The path needs to specify the file, including the `.zip` extension.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|true    |named   |False        |FilePath<br/>ExportFilePath<br/>Path|



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

Specify the package ID to export. This value is the standard package ID, for example `XYZ00123`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specify a package object to export. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a package to export.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WithContent**

Set this parameter to $true to export all content for the package and dependencies.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WithDependence**

Set this parameter to $true to export all package dependencies.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Export-CMPackage [-Comment <String>] [-DisableWildcardHandling] -FileName <String> [-Force] [-ForceWildcardHandling] -Id <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMPackage [-Comment <String>] [-DisableWildcardHandling] -FileName <String> [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMPackage [-Comment <String>] [-DisableWildcardHandling] -FileName <String> [-Force] [-ForceWildcardHandling] -Name <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
