Get-CMTaskSequenceGroup
-----------------------




### Synopsis
Gets a Configuration Manager task sequence group.



---


### Description

The Get-CMTaskSequenceGroup gets task sequence group(s) in a task sequence. The cmdlet supports pipeline from a task sequence object, and could be filtered by the name of the group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceGroup](New-CMTaskSequenceGroup)



* [Set-CMTaskSequenceGroup](Set-CMTaskSequenceGroup)



* [Remove-CMTaskSequenceGroup](Remove-CMTaskSequenceGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $ReferencedTaskSequence | Get-CMTaskSequenceGroup -StepName $gpName
```
The command gets the task sequence groups in a task sequence with name specified.


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



#### **InputObject**

Specifies a task sequence object.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **StepName**

Specifies the name of a step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specifies the ID of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specifies the name of a task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_TaskSequence_Group


* IResultObject#SMS_TaskSequence_Group






---


### Notes




---


### Syntax
```PowerShell
Get-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-StepName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceName <String> [<CommonParameters>]
```
