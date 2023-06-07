Get-CMTaskSequenceStep
----------------------




### Synopsis
Gets a Configuration Manager task sequence step.



---


### Description

The Get-CMTaskSequence cmdlet gets task sequence group or step object(s) from a specific task sequence. The cmdlet supports pipeline from a task sequence object, and can be filtered by the name of the group/step.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep)



* [Get-CMTaskSequenceStepCondition](Get-CMTaskSequenceStepCondition)



* [Remove-CMTaskSequenceStep](Remove-CMTaskSequenceStep)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>$ReferencedTaskSequence | Get-CMTaskSequenceStep -StepName $st1.Name
```
The comment gets a task sequence step by using the name.


---


### Parameters
#### **ActionClassName**

Specifies an action class name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-StepName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceName <String> [<CommonParameters>]
```
