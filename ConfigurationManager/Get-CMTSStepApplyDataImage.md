Get-CMTSStepApplyDataImage
--------------------------




### Synopsis
Get the Apply Data Image step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Apply Data Image step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepApplyDataImage (Remove-CMTSStepApplyDataImage.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Apply Data Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyDataImage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepApplyDataImage](New-CMTSStepApplyDataImage)



* [Remove-CMTSStepApplyDataImage](Remove-CMTSStepApplyDataImage)



* [Set-CMTSStepApplyDataImage](Set-CMTSStepApplyDataImage)



* [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [About task sequence steps: Apply Data Image](About task sequence steps: Apply Data Image)





---


### Examples
#### Example 1
```PowerShell
$tsName = "Custom task sequence"
$ts = Get-CMTaskSequence -Name $tsName -Fast

$tsStepNameApplyDataImg = "Apply data image"
$tsStepApplyDataImg = Get-CMTSStepApplyDataImage -InputObject $ts -StepName $tsStepNameApplyDataImg
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Apply Data Image step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Apply Data Image step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Apply Data Image step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Apply Data Image step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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
Get-CMTSStepApplyDataImage [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepApplyDataImage [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepApplyDataImage [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
