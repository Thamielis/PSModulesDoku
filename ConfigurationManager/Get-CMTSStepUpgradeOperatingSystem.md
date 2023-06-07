Get-CMTSStepUpgradeOperatingSystem
----------------------------------




### Synopsis
Get the Upgrade OS step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Upgrade OS step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepUpgradeOperatingSystem (Remove-CMTSStepUpgradeOperatingSystem.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Upgrade OS (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_UpgradeOS).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepUpgradeOperatingSystem](New-CMTSStepUpgradeOperatingSystem)



* [Remove-CMTSStepUpgradeOperatingSystem](Remove-CMTSStepUpgradeOperatingSystem)



* [Set-CMTSStepUpgradeOperatingSystem](Set-CMTSStepUpgradeOperatingSystem)



* [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [About task sequence steps: Apply OS Image](About task sequence steps: Apply OS Image)





---


### Examples
#### Example 1
```PowerShell
$tsName = "Default OS upgrade"
$tsUpg = Get-CMTaskSequence -Name $tsName -Fast

$tsStepNameUpgradeOs = "Upgrade Operating System"
$tsStepUpgradeOs = Get-CMTSStepUpgradeOperatingSystem -InputObject $tsUpg -StepName $tsStepNameUpgradeOs
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Upgrade OS step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Upgrade OS step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Upgrade OS step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Upgrade OS step.






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
Get-CMTSStepUpgradeOperatingSystem [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepUpgradeOperatingSystem [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepUpgradeOperatingSystem [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
