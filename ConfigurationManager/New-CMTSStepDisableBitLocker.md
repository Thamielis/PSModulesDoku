New-CMTSStepDisableBitLocker
----------------------------




### Synopsis
Create a Disable BitLocker step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Disable BitLocker step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Disable BitLocker](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_DisableBitLocker).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepDisableBitLocker](Get-CMTSStepDisableBitLocker)



* [Remove-CMTSStepDisableBitLocker](Remove-CMTSStepDisableBitLocker)



* [Set-CMTSStepDisableBitLocker](Set-CMTSStepDisableBitLocker)



* [About task sequence steps: Disable BitLocker](About task sequence steps: Disable BitLocker)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepDisableBitLocker -Name "Disable BitLocker" -RebootCount 12

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



#### **Drive**

Specify the drive letter to disable BitLocker on a specific drive. If you don't specify this parameter, the step disables BitLocker on the current OS drive.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |SpecificDrive|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **RebootCount**

Use this parameter to resume protection after Windows has been restarted the specified number of times. Instead of adding multiple instances of this step, set a value between `1` (default) and `15`.






|Type     |Required|Position|PipelineInput|Aliases     |
|---------|--------|--------|-------------|------------|
|`[Int32]`|false   |named   |False        |RebootNumber|



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
* IResultObject#SMS_TaskSequence_DisableBitLockerAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_DisableBitLockerAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_disablebitlockeraction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepDisableBitLocker [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-Drive <String>] [-ForceWildcardHandling] -Name <String> [-RebootCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
