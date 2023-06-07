New-CMTSStepApplyDataImage
--------------------------




### Synopsis
Create an Apply Data Image step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Apply Data Image step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Apply Data Image](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyDataImage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyDataImage](Get-CMTSStepApplyDataImage)



* [Remove-CMTSStepApplyDataImage](Remove-CMTSStepApplyDataImage)



* [Set-CMTSStepApplyDataImage](Set-CMTSStepApplyDataImage)



* [About task sequence steps: Apply Data Image](About task sequence steps: Apply Data Image)





---


### Examples
#### Example 1
```PowerShell
$pkgDataImg = Get-CMOperatingSystemImage -Name "Data image"
$step = New-CMTSStepApplyDataImage -Name "Apply data image" -ImagePackage $pkgDataImg -ImagePackageIndex 1

$tsName = "Custom task sequence"
$ts = Get-CMTaskSequence -Name $tsName -Fast

$ts | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
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



#### **Destination**

Specify the location where you want to apply this data image. If you don't specify this parameter, the default is `NextAvailableFormattedPartition`.


* `NextAvailableFormattedPartition`: Use the next sequential partition not already targeted by an Apply Operating System or Apply Data Image step in this task sequence.


* `SpecificDiskAndPartition`: Specify the disk number with the DestinationDisk parameter and the partition number with the DestinationPartition parameter.


* `SpecificLogicalDriverLetter`: Use the DestinationDriveLetter parameter to specify the logical drive letter assigned to the partition by Windows PE. This drive letter can be different from the drive letter assigned by the newly deployed OS.


* `LogicalDriverLetterInVariable`: Use the DestinationVariable parameter to specify the task sequence variable containing the drive letter assigned to the partition by Windows PE. This variable is typically set with the DiskNumberVariable parameter of the Set-CMTSStepPartitionDisk (Set-CMTSStepPartitionDisk.md) or [New-CMTSStepPartitionDisk](New-CMTSStepPartitionDisk.md)cmdlets for the Format and Partition Disk task sequence step.



Valid Values:

* NextAvailableFormattedPartition
* SpecificDiskAndPartition
* SpecificLogicalDriverLetter
* LogicalDriverLetterInVariable






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[DestinationType]`|false   |named   |False        |



#### **DestinationDisk**

When you use `-Destination SpecificDiskAndPartition`, use this parameter to specify the disk number. Specify an integer from `0` to `99`. Also use the DestinationPartition parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationDriveLetter**

When you use `-Destination SpecificLogicalDriverLetter`, use this parameter to specify the logical drive letter. Specify a drive letter from `C` to `Z`.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |DestinationLogicalDrive|



#### **DestinationPartition**

When you use `-Destination SpecificDiskAndPartition`, use this parameter to specify the partition number. Specify an integer from `1` to `99`. Also use the DestinationDisk parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationVariable**

When you use `-Destination LogicalDriverLetterInVariable`, use this parameter to specify the task sequence variable with the logical drive letter. The variable name needs to alphanumeric without spaces and fewer than 256 characters.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |DestinationVariableName|



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



#### **ImagePackage**

Specify a data image package object. The step applies the data from this image. Use the ImagePackageIndex parameter to set the image index.


To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ImagePackageIndex**

Specify an integer value of the image index. Use this parameter with the ImagePackage parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **WipePartition**

This setting is enabled by default, which deletes all content on the partition before applying the image.


Set this parameter to `$false` to not delete the prior contents of the partition. This action can be used to apply more content to a previously targeted partition.






|Type       |Required|Position|PipelineInput|Aliases                      |
|-----------|--------|--------|-------------|-----------------------------|
|`[Boolean]`|false   |named   |False        |WipePartitionBeforeApplyImage|



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
* IResultObject#SMS_TaskSequence_ApplyDataImageAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ApplyDataImageAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_applydataimageaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepApplyDataImage [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Destination {NextAvailableFormattedPartition | SpecificDiskAndPartition | SpecificLogicalDriverLetter | LogicalDriverLetterInVariable}] [-DestinationDisk <Int32>] [-DestinationDriveLetter <String>] [-DestinationPartition <Int32>] [-DestinationVariable <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -ImagePackage <IResultObject> -ImagePackageIndex <Int32> -Name <String> [-WipePartition <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
