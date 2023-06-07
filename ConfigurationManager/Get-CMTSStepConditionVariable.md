Get-CMTSStepConditionVariable
-----------------------------




### Synopsis
Get a task sequence variable condition from a task sequence step.



---


### Description

Use this cmdlet to get a task sequence variable condition object from a task sequence step. You can use this object to:



- View the details of the condition on the step.



- Copy the condition to another task sequence step.






When you use the New-CMTSStep\ or Set-CMTSStep\ cmdlets, provide this condition object with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [New-CMTSStepConditionVariable](New-CMTSStepConditionVariable)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1: View the details of a variable condition
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameRestart = "Restart in Windows PE"
$tsStepRestart = Get-CMTSStepReboot -InputObject $tsOsd -StepName $tsStepNameRestart

Get-CMTSStepConditionVariable -InputObject $tsStepRestart

SmsProviderObjectPath : SMS_TaskSequence_VariableConditionExpression
Operator              : equals
Value                 : false
Variable              : _SMSTSInWinPE
```

#### Example 2: Copy a condition to another step
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameRestart = "Restart in Windows PE"
$tsStepRestart = Get-CMTSStepReboot -InputObject $tsOsd -StepName $tsStepNameRestart

$condition = Get-CMTSStepConditionVariable -InputObject $tsStepRestart

$tsStepNameSetTSVar = "Set Task Sequence Variable"

Set-CMTSStepSetVariable -TaskSequenceName $tsNameOsd -StepName $tsStepNameSetTSVar -AddCondition $condition
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



#### **InputObject**

Specify a task sequence step object with a variable condition. To get this object, use one of the Get-CMTSStep cmdlets. For example, Get-CMTSStepApplyDataImage (Get-CMTSStepApplyDataImage.md).






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequenceStep|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_TaskSequence_VariableConditionExpression


* IResultObject#SMS_TaskSequence_VariableConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_VariableConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_variableconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMTSStepConditionVariable [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
