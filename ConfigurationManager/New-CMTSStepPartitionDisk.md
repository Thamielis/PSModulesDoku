New-CMTSStepPartitionDisk
-------------------------




### Synopsis
Create the Format and Partition Disk step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Format and Partition Disk step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Format and Partition Disk](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_FormatandPartitionDisk).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepPartitionDisk](Get-CMTSStepPartitionDisk)



* [Remove-CMTSStepPartitionDisk](Remove-CMTSStepPartitionDisk)



* [Set-CMTSStepPartitionDisk](Set-CMTSStepPartitionDisk)



* [New-CMTSPartitionSetting](New-CMTSPartitionSetting)



* [About task sequence steps: Format and Partition Disk](About task sequence steps: Format and Partition Disk)





---


### Examples
#### Example 1
```PowerShell
$partEfi = New-CMTSPartitionSetting -Name "EFI" -PartitionEfi -Size 500 -SizeUnit MB
$partMsr = New-CMTSPartitionSetting -Name "MSR" -PartitionMsr -Size 128 -SizeUnit MB
$partWin = New-CMTSPartitionSetting -Name "Windows" -PartitionPrimary -Size 99 -SizeUnit Percent -EnableDriveLetterAssignment $true -EnableQuickFormat $true -PartitionFileSystem NTFS -IsBootPartition $true
$partRec = New-CMTSPartitionSetting -Name "Recovery" -PartitionRecovery -Size 100 -SizeUnit Percent 

$step = New-CMTSStepPartitionDisk -Name "Partition Disk 0 - UEFI" -PartitionSetting @($partEfi,$partMsr,$partWin,$partRec) -DiskNumber 0 -DiskType Gpt -IsBootDisk $true

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



#### **DiskNumber**

Specify an integer for the physical disk number of the disk to format. The number is based on Windows disk enumeration ordering.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DiskNumberVariable**

Applies to version 2006 and later. Use a task sequence variable to specify the target disk to format. This variable option supports more complex task sequences with dynamic behaviors. For more information, see About task sequence steps - Format and Parition Disk (/mem/configmgr/osd/understand/task-sequence-steps#properties-for-format-and-partition-disk).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DiskType**

Specify the type of the disk to format:


* `Mbr`: Master Boot Record


* `Gpt`: GUID Partition Table



Valid Values:

* Mbr
* Gpt






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PartitionDiskStyle]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IsBootDisk**

For a new partition, set this parameter to `true` to make it the boot partition.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **PartitionSetting**

Specify an array of partition setting objects. To get this object, use the New-CMTSPartitionSetting (New-CMTSPartitionSetting.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases          |
|-------------------|--------|--------|-------------|-----------------|
|`[IResultObject[]]`|true    |named   |False        |PartitionSettings|



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
* IResultObject#SMS_TaskSequence_PartitionDiskAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_PartitionDiskAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_partitiondiskaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepPartitionDisk [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DiskNumber <Int32>] [-DiskNumberVariable <String>] [-DiskType {Mbr | Gpt}] [-ForceWildcardHandling] [-IsBootDisk <Boolean>] -Name <String> -PartitionSetting <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
