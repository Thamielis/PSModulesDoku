New-CMTSStepCaptureNetworkSettings
----------------------------------




### Synopsis
Create a Capture Network Settings step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Capture Network Settings step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Capture Network Settings](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureNetworkSettings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepCaptureNetworkSettings](Get-CMTSStepCaptureNetworkSettings)



* [Remove-CMTSStepCaptureNetworkSettings](Remove-CMTSStepCaptureNetworkSettings)



* [Set-CMTSStepCaptureNetworkSettings](Set-CMTSStepCaptureNetworkSettings)



* [About task sequence steps: Capture Network Settings](About task sequence steps: Capture Network Settings)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepCaptureNetworkSettings -Name "Capture Network Settings" -MigrateAdapterSettings $true -MigrateNetworkMembership $true

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



#### **MigrateAdapterSettings**

Set this parameter to `$true` to capture the network adapter configuration of the destination computer. It captures the following information:


* Global network settings


* Number of adapters


* The following network settings associated with each adapter: DNS, IP, and port filters






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MigrateNetworkMembership**

Set this parameter to `$true` to capture the domain and workgroup membership information of the destination computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_CaptureNetworkSettingsAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_CaptureNetworkSettingsAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_capturenetworksettingsaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepCaptureNetworkSettings [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrateAdapterSettings <Boolean>] [-MigrateNetworkMembership <Boolean>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
