Get-CMTSStepConditionQueryWmi
-----------------------------




### Synopsis
Get a WMI query condition from a task sequence step.



---


### Description

Use this cmdlet to get a WMI query condition object from a task sequence step. You can use this object to:



- View the details of the condition on the step.



- Copy the condition to another task sequence step.






When you use the New-CMTSStep\ or Set-CMTSStep\ cmdlets, provide this condition object with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



This cmdlet also returns the following types of conditions:



- OS language



- OS version and architecture





> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [New-CMTSStepConditionQueryWmi](New-CMTSStepConditionQueryWmi)



* [New-CMTSStepConditionOperatingSystem](New-CMTSStepConditionOperatingSystem)



* [New-CMTSStepConditionOperatingSystemLanguage](New-CMTSStepConditionOperatingSystemLanguage)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1: View the details of a WMI query condition
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameDynVar = "Set Dynamic Variables"
$tsStepDynVar = Get-CMTSStepSetDynamicVariable -InputObject $tsOsd -StepName $tsStepNameDynVar

Get-CMTSStepConditionQueryWmi -InputObject $tsStepDynVar

SmsProviderObjectPath : SMS_TaskSequence_WMIConditionExpression
Namespace             : root\cimv2
Query                 : SELECT OsLanguage FROM Win32_OperatingSystem WHERE OsLanguage='2108'
```

#### Example 2: Copy a condition to another step
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameDynVar = "Set Dynamic Variables"
$tsStepDynVar = Get-CMTSStepSetDynamicVariable -InputObject $tsOsd -StepName $tsStepNameDynVar

$condition = Get-CMTSStepConditionQueryWmi -InputObject $tsStepDynVar

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

Specify a task sequence step object with a WMI query condition. To get this object, use one of the Get-CMTSStep cmdlets. For example, Get-CMTSStepApplyDataImage (Get-CMTSStepApplyDataImage.md).






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequenceStep|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_TaskSequence_WMIConditionExpression


* IResultObject#SMS_TaskSequence_WMIConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_WMIConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_wmiconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMTSStepConditionQueryWmi [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
