New-CMTSStepReboot
------------------




### Synopsis
Create a Restart Computer step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Restart Computer step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Restart Computer](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RestartComputer).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepReboot](Get-CMTSStepReboot)



* [Remove-CMTSStepReboot](Remove-CMTSStepReboot)



* [Set-CMTSStepReboot](Set-CMTSStepReboot)



* [About task sequence steps: Restart Computer](About task sequence steps: Restart Computer)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepReboot -Name "Restart in Windows PE" -MessageTimeout 10 -NotificationMessage "The computer is restarting!" -RunAfterRestart WinPE

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



#### **MessageTimeout**

Specify the number of seconds before the destination computer restarts. The default is `60` seconds.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **NotificationMessage**

Specify a notification message to display to the user before the destination computer restarts.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RunAfterRestart**

Specify what to run after the computer restarts:


* `WinPE`: The boot image assigned to this task sequence


* `HardDisk`: The currently installed default OS



Valid Values:

* WinPE
* HardDisk






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[RunAfterRestartType]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_RebootAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RebootAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_rebootaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepReboot [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MessageTimeout <Int32>] -Name <String> [-NotificationMessage <String>] [-RunAfterRestart {WinPE | HardDisk}] [-Confirm] [-WhatIf] [<CommonParameters>]
```