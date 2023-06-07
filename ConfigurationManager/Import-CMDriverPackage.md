Import-CMDriverPackage
----------------------




### Synopsis
Import a driver package.



---


### Description

Use this cmdlet to import driver packages to the driver catalog. You can use the Export-CMDriverPackage (Export-CMDriverPackage.md)cmdlet to export a driver package to a .zip file.



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 6337796 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7. > > Starting in version 2103, if you try to use this cmdlet in a PowerShell version 7 session, it fails with the following error: `This cmdlet only supports the ".NET Framework" runtime.`



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMDriverPackage](Export-CMDriverPackage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [New-CMDriverPackage](New-CMDriverPackage)



* [Remove-CMDriverPackage](Remove-CMDriverPackage)



* [Set-CMDriverPackage](Set-CMDriverPackage)





---


### Examples
#### Example 1: Import a driver package
```PowerShell
Import-CMDriverPackage -ImportFilePath "\\Contoso02\main\driverpackages\DriverPackage.zip"
```

#### Example 2: Specify import action type
```PowerShell
$classVsAction = @{"SMS_Driver" = [Microsoft.ConfigurationManagement.AdminConsole.MigrationAssistant.ImportActionType]::AppendDriverCategories}
Import-CMDriverPackage -ImportFilePath $filePath -ImportActionTypeSpec $classVsAction
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



#### **ImportActionType**

If this package already exists in the site, use this parameter how to handle it. By default, Configuration Manager ignores duplicates.



Valid Values:

* NotSet
* Skip
* DirectImport
* Rename
* Overwrite
* ImportFail
* IgnoreDependencyFailure
* AppendDriverCategories
* OverwriteIgnoreDependencyFailure






|Type                |Required|Position|PipelineInput|Aliases                  |
|--------------------|--------|--------|-------------|-------------------------|
|`[ImportActionType]`|false   |named   |False        |ImportActionForAllObjects|



#### **ImportActionTypeSpec**

Use this parameter to specify import action type for different classes of object.






|Type         |Required|Position|PipelineInput|Aliases                         |
|-------------|--------|--------|-------------|--------------------------------|
|`[Hashtable]`|false   |named   |False        |ImportActionTypeForSpecificClass|



#### **ImportFilePath**

Specify the network path for the exported package. The cmdlet imports all packages in the file. The path needs to specify the file, including the `.zip` extension.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>Path|



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
Import-CMDriverPackage [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImportActionType {NotSet | Skip | DirectImport | Rename | Overwrite | ImportFail | IgnoreDependencyFailure | AppendDriverCategories | OverwriteIgnoreDependencyFailure}] [-ImportActionTypeSpec <Hashtable>] -ImportFilePath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
