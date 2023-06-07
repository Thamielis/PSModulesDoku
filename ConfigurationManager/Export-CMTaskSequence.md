Export-CMTaskSequence
---------------------




### Synopsis
Export a task sequence.



---


### Description

Use this cmdlet to export a task sequence from Configuration Manager. You can use the Import-CMTaskSequence (Import-CMTaskSequence.md)cmdlet to import a task sequence to another site.



> [!IMPORTANT] > This cmdlet doesn't support PowerShell 7 (/powershell/sccm/overview#support-for-powershell-version-7).<!-- 6337796 --> It requires the .NET Framework instead of .NET Core that's used with PowerShell version 7. > > Starting in version 2103, if you try to use this cmdlet in a PowerShell version 7 session, it fails with the following error: `This cmdlet only supports the ".NET Framework" runtime.`



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequence](New-CMTaskSequence)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)





---


### Examples
#### Example 1: Get a task sequence and export it
```PowerShell
$TaskSequence = Get-CMTaskSequence -Name "TaskSequence01"
Export-CMTaskSequence -InputObject $TaskSequence -ExportFilePath "\\Server1\TS\TaskSequence01.zip"
```

#### Example 2: Get a task sequence and use the pipeline to export it
```PowerShell
Get-CMTaskSequence -Name "TaskSequence02" | Export-CMTaskSequence -ExportFilePath "\\Server1\TS\TaskSequence02.zip"
```



---


### Parameters
#### **Comment**

Specify an optional administrator comment. This comment displays in the Import Task Sequence Wizard.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExportFilePath**

Specify the network path for the task sequence. The path needs to specify the file, including the `.zip` extension.






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



#### **InputObject**

Specify a task sequence object to export. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a task sequence to export.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TaskSequencePackageId**

Specify the task sequence ID to export. This value is the standard package ID, for example `XYZ00123`.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |PackageId<br/>Id|



#### **WithContent**

Set this parameter to $true to export all content for the task sequence and dependencies.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WithDependence**

Set this parameter to $true to export all task sequence dependencies.






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
Export-CMTaskSequence [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMTaskSequence [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -Name <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMTaskSequence [-Comment <String>] [-DisableWildcardHandling] -ExportFilePath <String> [-Force] [-ForceWildcardHandling] -TaskSequencePackageId <String> [-WithContent <Boolean>] [-WithDependence <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
