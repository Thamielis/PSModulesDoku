Publish-CMPrestageContentTaskSequence
-------------------------------------




### Synopsis
Distributes the content that a task sequence uses to a distribution point.



---


### Description

The Publish-CMPrestageContentTaskSequence cmdlet distributes the content that a task sequence uses to a distribution point. Optionally, you can exclude the application dependencies for applications indicated in the task sequence.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Publish-CMPrestageContent](Publish-CMPrestageContent)





---


### Examples
#### Example 1: Publish content required by a task sequence
```PowerShell
PS XYZ:\>Publish-CMPrestageContentTaskSequence -DistributionPointName "distribution-server.contoso.com" -FolderName "ToBePublished" -TaskSequenceName "ContosoDeploymentSequence"
```
This command copies content required by the task sequence ContosoDeploymentSequence to the distribution point distribution-server.contoso.com.


---


### Parameters
#### **Description**

Specifies a description for the content to prestage.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointName**

Specifies the name of a distribution point that is associated with the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FolderName**

Specifies a folder name. The folder that you specify contains prestaged content files.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IgnoreApplicationDependency**








|Type      |Required|Position|PipelineInput|Aliases                                                                |
|----------|--------|--------|-------------|-----------------------------------------------------------------------|
|`[Switch]`|false   |named   |False        |DisableIncludeApplicationDependencies<br/>IgnoreApplicationDependencies|



#### **TaskSequence**

Specifies a task sequence object. To obtain a task sequence object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **TaskSequenceId**

Specifies an array of IDs of task sequences.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|true    |named   |False        |TaskSequenceIds|



#### **TaskSequenceName**

Specifies an array of names of task sequences.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|true    |named   |False        |TaskSequenceNames|



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
Publish-CMPrestageContentTaskSequence [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FolderName <String> [-ForceWildcardHandling] [-IgnoreApplicationDependency] -TaskSequence <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContentTaskSequence [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FolderName <String> [-ForceWildcardHandling] [-IgnoreApplicationDependency] -TaskSequenceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Publish-CMPrestageContentTaskSequence [-Description <String>] [-DisableWildcardHandling] -DistributionPointName <String> -FolderName <String> [-ForceWildcardHandling] [-IgnoreApplicationDependency] -TaskSequenceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
