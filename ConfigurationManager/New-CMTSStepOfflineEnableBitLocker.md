New-CMTSStepOfflineEnableBitLocker
----------------------------------




### Synopsis
Create a Pre-provision BitLocker step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Pre-provision BitLocker step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this task sequence step, see [About task sequence steps](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_PreProvisionBitLocker).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepOfflineEnableBitLocker](Get-CMTSStepOfflineEnableBitLocker)



* [Remove-CMTSStepOfflineEnableBitLocker](Remove-CMTSStepOfflineEnableBitLocker)



* [Set-CMTSStepOfflineEnableBitLocker](Set-CMTSStepOfflineEnableBitLocker)



* [About task sequence steps: Pre-provision BitLocker](About task sequence steps: Pre-provision BitLocker)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepOfflineEnableBitLocker -Name "Pre-provision BitLocker" -Drive "C:" -EncryptionMethod AES_256 -EnableSkipWhenTpmInvalid $false

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



#### **Disk**

Specify the specific disk number to encrypt. Use this parameter with the -Partition parameter.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|false   |named   |False        |DestinationDisk|



#### **Drive**

Specify the logical drive letter to encrypt. For example, `C:`






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |DestinationDrive|



#### **EnableSkipWhenTpmInvalid**

Set this parameter to `true` to skip this step for computers that don't have a TPM or when the TPM isn't enabled.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EncryptionMethod**

Applies to version 2006 and later. Use this parameter to specify the disk encryption mode. By default or if not specified, the step continues to use the default encryption method for the OS version.



Valid Values:

* DoNotSpecify
* AES_128
* AES_256
* XTS_AES128
* XTS_AES256
* TotalCount






|Type                    |Required|Position|PipelineInput|Aliases             |
|------------------------|--------|--------|-------------|--------------------|
|`[DiskEncryptionMethod]`|false   |named   |False        |DiskEncryptionMethod|



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



#### **Partition**

Specify the specific partition number to encrypt. Use this parameter with the -Disk parameter.






|Type     |Required|Position|PipelineInput|Aliases             |
|---------|--------|--------|-------------|--------------------|
|`[Int32]`|false   |named   |False        |DestinationPartition|



#### **VariableName**

Specify a task sequence variable to identify the logical drive letter as the destination for BitLocker.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |DestinationVariable|



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
* IResultObject#SMS_TaskSequence_OfflineEnableBitLockerAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_OfflineEnableBitLockerAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_offlineenablebitlockeraction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepOfflineEnableBitLocker [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-Disk <Int32>] [-Drive <String>] [-EnableSkipWhenTpmInvalid <Boolean>] [-EncryptionMethod {DoNotSpecify | AES_128 | AES_256 | XTS_AES128 | XTS_AES256 | TotalCount}] [-ForceWildcardHandling] -Name <String> [-Partition <Int32>] [-VariableName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
