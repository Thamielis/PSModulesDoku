Import-CMBaseline
-----------------




### Synopsis
Import a configuration baseline.



---


### Description

Use this cmdlet to import one or more configuration baselines from files.



You can import a configuration baseline from a cabinet (`.cab`) file that conforms to the Service Modeling Language (SML) schema. For example, you might import data previously exported from Configuration Manager or included in a configuration pack from a vendor.



When you import a baseline configuration, you have the option of creating a local copy. You can then modify that baseline copy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)





---


### Examples
#### Example 1: Import a baseline
```PowerShell
Import-CMBaseline -FileName "\\ContosoServer01\Public\CM\BaselineW2K8.cab"
```

#### Example 2: Import multiple baselines
```PowerShell
Import-CMBaseline -FileName "\\ContosoServer01\Public\CM\BaselineW2K8.cab","\\ContosoServer01\Public\CM\BaselineWin7.cab" -DuplicateWhileImporting
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DuplicateWhileImporting**

Add this parameter to duplicate the baseline when it imports. When you duplicate a baseline, you can then modify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileName**

Specify an array of cabinet (`.cab`) file names to import.






|Type        |Required|Position|PipelineInput|Aliases                                                                                       |
|------------|--------|--------|-------------|----------------------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |FilePath<br/>ImportFilePath<br/>Path<br/>FileNames<br/>FilePaths<br/>ImportFilePaths<br/>Paths|



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
Import-CMBaseline [-DisableWildcardHandling] [-DuplicateWhileImporting] -FileName <String[]> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
