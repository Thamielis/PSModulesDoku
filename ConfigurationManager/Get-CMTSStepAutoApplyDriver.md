Get-CMTSStepAutoApplyDriver
---------------------------




### Synopsis
Get the Auto Apply Drivers step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Auto Apply Drivers step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepAutoApplyDriver (Remove-CMTSStepAutoApplyDriver.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Auto Apply Drivers (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_AutoApplyDrivers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepAutoApplyDriver](New-CMTSStepAutoApplyDriver)



* [Remove-CMTSStepAutoApplyDriver](Remove-CMTSStepAutoApplyDriver)



* [Set-CMTSStepAutoApplyDriver](Set-CMTSStepAutoApplyDriver)



* [About task sequence steps: Auto Apply Drivers](About task sequence steps: Auto Apply Drivers)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameAutoApplyDvr = "Auto Apply Drivers"
$tsStepAutoApplyDvr = Get-CMTSStepAutoApplyDriver -InputObject $tsOsd -StepName $tsStepNameAutoApplyDvr
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Auto Apply Drivers step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Auto Apply Drivers step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Auto Apply Drivers step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Auto Apply Drivers step.






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
Get-CMTSStepAutoApplyDriver [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepAutoApplyDriver [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepAutoApplyDriver [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
