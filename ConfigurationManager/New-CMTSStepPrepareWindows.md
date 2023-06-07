New-CMTSStepPrepareWindows
--------------------------




### Synopsis
Create the Prepare Windows for Capture step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Prepare Windows for Capture step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Prepare Windows for Capture](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_PrepareWindowsforCapture).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepPrepareWindows](Get-CMTSStepPrepareWindows)



* [Remove-CMTSStepPrepareWindows](Remove-CMTSStepPrepareWindows)



* [Set-CMTSStepPrepareWindows](Set-CMTSStepPrepareWindows)



* [About task sequence steps: Prepare Windows for Capture](About task sequence steps: Prepare Windows for Capture)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepPrepareWindows -Name "Prepare Windows for Capture" -BuildDriverList $false -KeepActivation $true

$tsNameOsd = "Default OS deployment and capture"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **BuildDriverList**

Set this parameter to `$true` to have Sysprep automatically build a list of mass storage drivers from the reference computer. This option enables the Build Mass Storage Drivers option in the sysprep.inf file on the reference computer.






|Type       |Required|Position|PipelineInput|Aliases                                |
|-----------|--------|--------|-------------|---------------------------------------|
|`[Boolean]`|false   |named   |False        |AutomaticallyBuildMassStorageDriverList|



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



#### **KeepActivation**

Set this parameter to `$true` to prevent Sysprep from resetting the product activation flag.






|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |DoNotResetActivationFlag|



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



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
* IResultObject#SMS_TaskSequence_PrepareOSAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_PrepareOSAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_prepareosaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepPrepareWindows [-BuildDriverList <Boolean>] [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-KeepActivation <Boolean>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
