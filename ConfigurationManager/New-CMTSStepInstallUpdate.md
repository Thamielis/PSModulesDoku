New-CMTSStepInstallUpdate
-------------------------




### Synopsis
Create an Install Software Updates step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Install Software Updates step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Install Software Updates](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallSoftwareUpdates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepInstallUpdate](Get-CMTSStepInstallUpdate)



* [Remove-CMTSStepInstallUpdate](Remove-CMTSStepInstallUpdate)



* [Set-CMTSStepInstallUpdate](Set-CMTSStepInstallUpdate)



* [About task sequence steps: Install Software Updates](About task sequence steps: Install Software Updates)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepInstallUpdate -Name "Install Software Updates" -Target All -UseCache $true -RetryCount 5

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



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **RetryCount**

If one of the updates unexpectedly restarts the computer, retry this step for the number of times that you specify with this parameter. By default, the step retries twice. Specify an integer value from `1` to `5`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Target**

Specify a value for the type of updates to install:


* `All`: Install all available software updates. First deploy these updates to a collection of which the computer is a member.


* `Mandatory`: Install all mandatory software updates with administrator-defined installation deadlines.



Valid Values:

* All
* Mandatory






|Type          |Required|Position|PipelineInput|Aliases                             |
|--------------|--------|--------|-------------|------------------------------------|
|`[TargetType]`|false   |named   |False        |InstallUpdateBasedOnTypeOfDeployment|



#### **UseCache**

Set this parameter to `$true` to evaluate software updates from cached scan results.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableEvaluateFromCache|



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
* IResultObject#SMS_TaskSequence_InstallUpdateAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_InstallUpdateAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_installupdateaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepInstallUpdate [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-RetryCount <Int32>] [-Target {All | Mandatory}] [-UseCache <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
