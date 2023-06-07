Get-CMTaskSequenceStepCondition
-------------------------------




### Synopsis
Get a condition on a task sequence step.



---


### Description

Use this cmdlet to get a condition on a task sequence step. The task sequence evaluates the condition before it runs the step or group. For more information, see How to use task sequence variables (/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_access-condition).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequenceStep](Get-CMTaskSequenceStep)



* [Get-CMTaskSequenceGroup](Get-CMTaskSequenceGroup)





---


### Examples
#### Example 1: Get a default condition
```PowerShell
$tsname = "Default IPU"
$tsgroup = "Post-Processing"
$ts = Get-CMTaskSequence -Name $tsname

$ts | Get-CMTaskSequenceGroup -StepName $tsgroup | Get-CMTaskSequenceStepCondition

SmsProviderObjectPath : SMS_TaskSequence_VariableConditionExpression
Operator              : equals
Value                 : false
Variable              : _SMSTSSetupRollback
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

Specify a task sequence group or step object. To get this object, use the Get-CMTaskSequenceGroup (Get-CMTaskSequenceGroup.md) or [Get-CMTaskSequenceStep](Get-CMTaskSequenceStep.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequenceStep|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_TaskSequence_Condition


* IResultObject#SMS_TaskSequence_Condition






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_Condition server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_condition-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMTaskSequenceStepCondition [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
