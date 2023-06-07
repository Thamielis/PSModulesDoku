New-CMTSStepRunTaskSequence
---------------------------




### Synopsis
Create a Run Task Sequence step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Run Task Sequence step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Run Task Sequence](/mem/configmgr/osd/understand/task-sequence-steps#child-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRunTaskSequence](Get-CMTSStepRunTaskSequence)



* [Remove-CMTSStepRunTaskSequence](Remove-CMTSStepRunTaskSequence)



* [Set-CMTSStepRunTaskSequence](Set-CMTSStepRunTaskSequence)



* [About task sequence steps: Run Task Sequence](About task sequence steps: Run Task Sequence)





---


### Examples
#### Example 1
```PowerShell
$tsNameChild = "SubTS: Partition disks"
$tsChild = Get-CMTaskSequence -Name $tsNameChild -Fast
$step = New-CMTSStepRunTaskSequence -Name "Run Task Sequence" -RunTaskSequence $tsChild

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **Condition**

Specify a condition object to use with this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Disable**

Add this parameter to disable this task sequence step.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |DisableThisStep|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **RunTaskSequence**

Specify an object for the task sequence that you want this step to run. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases|
|-----------------|--------|--------|-------------|-------|
|`[IResultObject]`|true    |named   |False        |Child  |



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
* IResultObject#SMS_TaskSequence_SubTasksequence






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_SubTasksequence server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_subtasksequence-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepRunTaskSequence [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -RunTaskSequence <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
