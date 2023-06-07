New-CMTSStepApplyOperatingSystem
--------------------------------




### Synopsis
Create an Apply OS Image step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Apply OS Image step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Apply OS Image](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyOperatingSystemImage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyOperatingSystem](Get-CMTSStepApplyOperatingSystem)



* [Remove-CMTSStepApplyOperatingSystem](Remove-CMTSStepApplyOperatingSystem)



* [Set-CMTSStepApplyOperatingSystem](Set-CMTSStepApplyOperatingSystem)



* [About task sequence steps: Apply OS Image](About task sequence steps: Apply OS Image)





---


### Examples
#### Example 1
```PowerShell
$osImgPkg = Get-CMOperatingSystemImage -Name "OSImagePkg01"
$step = New-CMTSStepApplyOperatingSystem -Name "Apply OS image" -ImagePackage $osImgPkg -ImagePackageIndex 1

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



#### **ConfigFileName**

Specify the file name of an unattended or Sysprep answer file to use for a custom installation. Use this parameter with the ConfigFilePackage parameter.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |AnswerFileName|



#### **ConfigFilePackage**

Specify a package object that includes the unattended or Sysprep answer file to use for a custom installation. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet. Use this parameter with the ConfigFileName parameter.






|Type             |Required|Position|PipelineInput|Aliases          |
|-----------------|--------|--------|-------------|-----------------|
|`[IResultObject]`|false   |named   |False        |AnswerFilePackage|



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

Specify the location where you want to apply this OS. If you don't specify this parameter, the default is `NextAvailableFormattedPartition`.


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

Specify an OS image package object. The step applies the OS from this image. Use the ImagePackageIndex parameter to set the image index.


To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ImagePackageIndex**

Specify an integer value of the image index. Use this parameter with the ImagePackage parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **InstallPackage**

Specify an OS upgrade package object. The step applies the OS from this original installation source. Use the InstallPackageIndex parameter to set the edition.


To get this object, use the Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases       |
|-----------------|--------|--------|-------------|--------------|
|`[IResultObject]`|false   |named   |False        |UpgradePackage|



#### **InstallPackageIndex**

Specify an integer value of the OS upgrade package edition. Use this parameter with the InstallPackage parameter.






|Type     |Required|Position|PipelineInput|Aliases            |
|---------|--------|--------|-------------|-------------------|
|`[Int32]`|false   |named   |False        |UpgradePackageIndex|



#### **LayeredDriver**

Starting in version 2107, use this parameter to select other types of keyboards that are common with Japanese and Korean languages. Specify an integer value for the layered driver to install with Windows. Use the same values as the OsdLayeredDriver (/mem/configmgr/osd/understand/task-sequence-variables#OsdLayeredDriver)task sequence variable.



Valid Values:

* DoNotSpecify
* Driver1
* Driver2
* Driver3
* Driver4
* Driver5
* Driver6






|Type                |Required|Position|PipelineInput|Aliases       |
|--------------------|--------|--------|-------------|--------------|
|`[OsdLayeredDriver]`|false   |named   |False        |KeyboardDriver|



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **RunFromNet**

Set this parameter to `$true` to allow the task sequence to apply the OS image directly from the distribution point.


For greatest security, it's recommended to not enable this setting. This option is designed for use on devices with limited storage capacity. For more information, see Access content directly from the distribution point (/mem/configmgr/osd/understand/task-sequence-steps#access-content-directly-from-the-distribution-point).






|Type       |Required|Position|PipelineInput|Aliases                         |
|-----------|--------|--------|-------------|--------------------------------|
|`[Boolean]`|false   |named   |False        |AllowAccessFromDistributionPoint|



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
* IResultObject#SMS_TaskSequence_ApplyOperatingSystemAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ApplyOperatingSystemAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_applyoperatingsystemaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepApplyOperatingSystem [-Condition <IResultObject[]>] [-ConfigFileName <String>] [-ConfigFilePackage <IResultObject>] [-ContinueOnError] [-Description <String>] [-Destination {NextAvailableFormattedPartition | SpecificDiskAndPartition | SpecificLogicalDriverLetter | LogicalDriverLetterInVariable}] [-DestinationDisk <Int32>] [-DestinationDriveLetter <String>] [-DestinationPartition <Int32>] [-DestinationVariable <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImagePackage <IResultObject>] [-ImagePackageIndex <Int32>] [-InstallPackage <IResultObject>] [-InstallPackageIndex <Int32>] [-LayeredDriver {DoNotSpecify | Driver1 | Driver2 | Driver3 | Driver4 | Driver5 | Driver6}] -Name <String> [-RunFromNet <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
