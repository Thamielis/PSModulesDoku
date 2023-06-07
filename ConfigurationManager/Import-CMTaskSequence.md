Import-CMTaskSequence
---------------------




### Synopsis
Import a task sequence.



---


### Description

Use this cmdlet to import a task sequence into Configuration Manager. You can use the Export-CMTaskSequence (Export-CMTaskSequence.md)cmdlet to export a task sequence to a .zip file.



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 6337796 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7. > > Starting in version 2103, if you try to use this cmdlet in a PowerShell version 7 session, it fails with the following error: `This cmdlet only supports the ".NET Framework" runtime.`



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMTaskSequence](Export-CMTaskSequence)



* [New-CMTaskSequence](New-CMTaskSequence)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)





---


### Examples
#### Example 1: Import a task sequence
```PowerShell
Import-CMTaskSequence -ImportFilePath "\\Server1\TS\TaskSequence.zip"
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



#### **IgnoreDependency**

Add this parameter to ignore dependencies in the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ImportActionType**

If this task sequence already exists in the site, use this parameter how to handle it. By default, Configuration Manager ignores duplicates.



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



#### **Path**

Specify the network path for the exported task sequence. The cmdlet imports all task sequences in the file. The path needs to specify the file, including the `.zip` extension.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ImportFilePath|



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
Import-CMTaskSequence [-DisableWildcardHandling] [-ForceWildcardHandling] [-IgnoreDependency] [-ImportActionType {NotSet | Skip | DirectImport | Rename | Overwrite | ImportFail | IgnoreDependencyFailure | AppendDriverCategories | OverwriteIgnoreDependencyFailure}] [-ImportActionTypeSpec <Hashtable>] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
