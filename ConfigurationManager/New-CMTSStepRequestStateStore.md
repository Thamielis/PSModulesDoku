New-CMTSStepRequestStateStore
-----------------------------




### Synopsis
Create the Request State Store step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Request State Store step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Request State Store](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RequestStateStore).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRequestStateStore](Get-CMTSStepRequestStateStore)



* [Remove-CMTSStepRequestStateStore](Remove-CMTSStepRequestStateStore)



* [Set-CMTSStepRequestStateStore](Set-CMTSStepRequestStateStore)



* [About task sequence steps: Request State Store](About task sequence steps: Request State Store)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepRequestStateStore -Name "Request State Store" -RequestOption Capture -FallbackToAccount $false -RetryCount 3 -RetryTime 60

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



#### **FallbackToAccount**

When you set this value to `$true`, if the task sequence can't access the state migration point using the computer account, it uses the network access account credentials to connect. This option is less secure because other computers could use the network access account to access the stored state. This option might be necessary if the destination computer isn't domain joined.


For more information, see Network access account (/mem/configmgr/core/plan-design/hierarchy/accounts#network-access-account).






|Type       |Required|Position|PipelineInput|Aliases      |
|-----------|--------|--------|-------------|-------------|
|`[Boolean]`|false   |named   |False        |FallbackToNaa|



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



#### **RequestOption**

Specify the reason to request access to the state migration point:


* `Capture`: Capture state from the computer. If the Configuration Manager site has multiple active state migration points, this step finds a state migration point with available disk space. The task sequence queries the management point for a list of state migration points, and then evaluates each until it finds one that meets the minimum requirements.


* `Restore`: Restore state from another computer. If there are multiple state migration points, this step finds the state migration point that has the state for the destination computer.



Valid Values:

* Capture
* Restore






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[RequestType]`|false   |named   |False        |



#### **RetryCount**

Specify the number of times that this step tries to find an appropriate state migration point before failing.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **RetryTime**

Specify the amount of time in seconds that the task sequence step waits between retry attempts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_RequestStateStoreAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RequestStateStoreAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_requeststatestoreaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepRequestStateStore [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-FallbackToAccount <Boolean>] [-ForceWildcardHandling] -Name <String> [-RequestOption {Capture | Restore}] [-RetryCount <Int32>] [-RetryTime <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
