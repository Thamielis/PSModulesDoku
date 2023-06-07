New-CMTSStepSetVariable
-----------------------




### Synopsis
Create a Set Task Sequence Variable step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Set Task Sequence Variable step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Set Task Sequence Variable](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_SetTaskSequenceVariable).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepSetVariable](Get-CMTSStepSetVariable)



* [Remove-CMTSStepSetVariable](Remove-CMTSStepSetVariable)



* [Set-CMTSStepSetVariable](Set-CMTSStepSetVariable)



* [About task sequence steps: Set Task Sequence Variable](About task sequence steps: Set Task Sequence Variable)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepSetVariable -Name "Set Task Sequence Variable" -TaskSequenceVariable "OSDSetupAdditionalUpgradeOptions" -TaskSequenceVariableValue "/ReflectDrivers"

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

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IsMasked**

Set this parameter to `$true` to mask sensitive data stored in task sequence variables. For example, when specifying a password.






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |IsHidden<br/>IsMask|



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **TaskSequenceVariable**

Specify the name of a task sequence built-in or action variable, or specify your own user-defined variable name. For more information, see How to use task sequence variables in Configuration Manager (/mem/configmgr/osd/understand/using-task-sequence-variables) and the reference of [Task sequence variables](/mem/configmgr/osd/understand/task-sequence-variables).


Use the TaskSequenceVariableValue parameter to set the value.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |VariableName|



#### **TaskSequenceVariableValue**

The task sequence sets the TaskSequenceVariable to this value. Set this task sequence variable to the value of another task sequence variable with the syntax `%varname%`.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |VariableValue|



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
* IResultObject#SMS_TaskSequence_SetVariableAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_SetVariableAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_setvariableaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepSetVariable [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMasked <Boolean>] -Name <String> -TaskSequenceVariable <String> [-TaskSequenceVariableValue <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
