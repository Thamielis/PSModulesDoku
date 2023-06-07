Get-CMTSStepRunCommandLine
--------------------------




### Synopsis
Get the Run Command Line step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Run Command Line step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepRunCommandLine (Remove-CMTSStepRunCommandLine.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Run Command Line (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RunCommandLine).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepRunCommandLine](New-CMTSStepRunCommandLine)



* [Remove-CMTSStepRunCommandLine](Remove-CMTSStepRunCommandLine)



* [Set-CMTSStepRunCommandLine](Set-CMTSStepRunCommandLine)



* [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [About task sequence steps: Run Command Line](About task sequence steps: Run Command Line)





---


### Examples
#### Example 1
```PowerShell
$tsName = "Custom task sequence"
$ts = Get-CMTaskSequence -Name $tsName -Fast

$tsStepNameRunCmd = "Run Command Line"
$tsStepRunCmd = Get-CMTSStepRunCommandLine -InputObject $ts -StepName $tsStepNameRunCmd
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Run Command Line step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Run Command Line step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Run Command Line step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Run Command Line step.






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
Get-CMTSStepRunCommandLine [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepRunCommandLine [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepRunCommandLine [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
