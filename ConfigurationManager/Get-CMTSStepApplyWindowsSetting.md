Get-CMTSStepApplyWindowsSetting
-------------------------------




### Synopsis
Get the Apply Windows Settings step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Apply Windows Settings step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepApplyWindowsSetting (Remove-CMTSStepApplyWindowsSetting.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepApplyWindowsSetting](New-CMTSStepApplyWindowsSetting)



* [Remove-CMTSStepApplyWindowsSetting](Remove-CMTSStepApplyWindowsSetting)



* [Set-CMTSStepApplyWindowsSetting](Set-CMTSStepApplyWindowsSetting)



* [About task sequence steps: Apply Windows Settings](About task sequence steps: Apply Windows Settings)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameApplyWinSet = "Apply Windows Settings"
$tsStepApplyWinSet = Get-CMTSStepApplyWindowsSetting -InputObject $tsOsd -StepName $tsStepNameApplyWinSet
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Apply Windows Settings step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Apply Windows Settings step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Apply Windows Settings step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Apply Windows Settings step.






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
Get-CMTSStepApplyWindowsSetting [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepApplyWindowsSetting [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepApplyWindowsSetting [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```