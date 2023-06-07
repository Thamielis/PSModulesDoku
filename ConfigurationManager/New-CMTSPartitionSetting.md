New-CMTSPartitionSetting
------------------------




### Synopsis
Create a disk partition object to use with the Format and Partition Disk task sequence step.



---


### Description

This cmdlet creates a disk partition object to use with the Format and Partition Disk task sequence step. Use this cmdlet to define the partition settings, and then use that object with the -PartitionSetting parameter of the New-CMTSStepPartitionDisk (new-cmtssteppartitiondisk.md) or [Set-CMTSStepPartitionDisk](set-cmtssteppartitiondisk.md)cmdlets.



You can create the following types of partition settings objects, based on the switch parameter that you use with this cmdlet:



- PartitionPrimary : Primary partition - PartitionEfi EFI partition - PartitionExtended : Extended partition - PartitionHidden : Hidden partition - PartitionLogical : Logical partition - PartitionMsr : MSR partition - PartitionRecovery : Recovery partition



If you don't specify a partition switch parameter, the cmdlet creates a primary partition settings object.



For more information, see Format and Partition Disk: Volume (/mem/configmgr/osd/understand/task-sequence-steps#volume).



---


### Related Links
* [Get-CMTSStepPartitionDisk](Get-CMTSStepPartitionDisk)



* [New-CMTSStepPartitionDisk](New-CMTSStepPartitionDisk)



* [Set-CMTSStepPartitionDisk](Set-CMTSStepPartitionDisk)



* [About task sequence steps - Format and Partition Disk](About task sequence steps - Format and Partition Disk)



* [UEFI/GPT-based hard drive partitions](UEFI/GPT-based hard drive partitions)



* [BIOS/MBR-based hard drive partitions](BIOS/MBR-based hard drive partitions)





---


### Examples
#### Example 1: Create settings for an EFI partition
```PowerShell
$partEfi = New-CMTSPartitionSetting -Name "EFI" -PartitionEfi -Size 500 -SizeUnit MB
```

#### Example 2: Create settings for an MSR partition
```PowerShell
$partMsr = New-CMTSPartitionSetting -Name "MSR" -PartitionMsr -Size 128 -SizeUnit MB
```

#### Example 3: Create settings for a Windows primary partition
```PowerShell
$partWin = New-CMTSPartitionSetting -Name "Windows" -PartitionPrimary -Size 99 -SizeUnit Percent -EnableDriveLetterAssignment $true -EnableQuickFormat $true -PartitionFileSystem NTFS -IsBootPartition $true
```

#### Example 4: Create settings for a recovery partition
```PowerShell
$partRec = New-CMTSPartitionSetting -Name "Recovery" -PartitionRecovery -Size 100 -SizeUnit Percent
```

#### Example 5: View the partition setting details for a step
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameFormatDisk = "Partition Disk 0 - UEFI"
$tsStepFormatDisk = Get-CMTSStepPartitionDisk -InputObject $tsOsd -StepName $tsStepNameFormatDisk

$tsStepFormatDisk.Partitions[0]
```
You can use this process to copy partition settings between steps or task sequences. Save this partition settings object as a variable and then add it to another step.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDriveLetterAssignment**

Set this parameter to `true` to let Configuration Manager assign a drive letter to the partition.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableQuickFormat**

Set this parameter to `true` to let Configuration Manager do a quick format of the partition.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IsBootPartition**

Set this parameter to `true` to make this partition the boot partition.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify a name for the partition.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|false   |named   |False        |PartitionName<br/>VolumeName|



#### **PartitionEfi**

Add this parameter to make the partition type EFI .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionExtended**

Add this parameter to make the partition type Extended .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionFileSystem**

Specify the file system to format the partition.



Valid Values:

* None
* Ntfs
* Fat32






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[FileSystemType]`|false   |named   |False        |



#### **PartitionHidden**

Add this parameter to make the partition type Hidden .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionLogical**

Add this parameter to make the partition type Logical .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionMsr**

Add this parameter to make the partition type MSR .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionPrimary**

Add this parameter to make the partition type Primary .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PartitionRecovery**

Add this parameter to make the partition type Recovery .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Size**

Specify an integer value for the size of the partition. Use this parameter with the -SizeUnit parameter. If -SizeUnit is `Percent`, then specify a number between 1-100 for this parameter. If -SizeUnit is `MB` or `GB`, specify a number for the specific partition size.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SizeUnit**

Specify the unit type for the size. Use this parameter with the -Size parameter.


* `Percent`: Use -Size to set the partition to a percentage of remaining free space on the disk.


* `MB` or `GB`: Use -Size to set a specific size for the partition.



Valid Values:

* MB
* GB
* Percent






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SizeUnitType]`|false   |named   |False        |



#### **Variable**

By default, Configuration Manager assigns the next available drive letter to this partition. To save this drive letter for future use, set a custom task sequence variable with this parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_PartitionSettings






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_PartitionSettings server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_partitionsettings-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-EnableDriveLetterAssignment <Boolean>] [-EnableQuickFormat <Boolean>] [-ForceWildcardHandling] [-IsBootPartition <Boolean>] [-Name <String>] [-PartitionFileSystem {Ntfs | Fat32}] -PartitionPrimary [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Variable <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionEfi [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionExtended [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionHidden [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionLogical [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionMsr [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSPartitionSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -PartitionRecovery [-Size <Int32>] [-SizeUnit {MB | GB | Percent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
