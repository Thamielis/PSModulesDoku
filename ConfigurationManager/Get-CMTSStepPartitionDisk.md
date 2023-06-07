Get-CMTSStepPartitionDisk
-------------------------




### Synopsis
Get the Format and Partition Disk step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Format and Partition Disk step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepPartitionDisk (Remove-CMTSStepPartitionDisk.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Format and Partition Disk (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_FormatandPartitionDisk).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepPartitionDisk](New-CMTSStepPartitionDisk)



* [Remove-CMTSStepPartitionDisk](Remove-CMTSStepPartitionDisk)



* [Set-CMTSStepPartitionDisk](Set-CMTSStepPartitionDisk)



* [New-CMTSPartitionSetting](New-CMTSPartitionSetting)



* [About task sequence steps: Format and Partition Disk](About task sequence steps: Format and Partition Disk)





---


### Examples
#### Example 1: Get the step from a task sequence
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameFormatDisk = "Partition Disk 0 - UEFI"
$tsStepFormatDisk = Get-CMTSStepPartitionDisk -InputObject $tsOsd -StepName $tsStepNameFormatDisk
```

#### Example 2: View the partition setting details for a step
```PowerShell
$tsStepFormatDisk = Get-CMTSStepPartitionDisk -InputObject $tsOsd -StepName $tsStepNameFormatDisk

$tsStepFormatDisk.Partitions[0]
```
You can use this process to copy partition settings between steps or task sequences. Save this partition settings object as a variable and then add it to another step.


---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Format and Partition Disk step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Format and Partition Disk step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Format and Partition Disk step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Format and Partition Disk step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMTSStepPartitionDisk [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepPartitionDisk [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepPartitionDisk [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
