Remove-CMTSStepCaptureWindowsSettings
-------------------------------------




### Synopsis
Remove the Capture Windows Settings step from a task sequence.



---


### Description

Use this cmdlet to remove an instance of the Capture Windows Settings step from a task sequence.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepCaptureWindowsSettings](Get-CMTSStepCaptureWindowsSettings)



* [New-CMTSStepCaptureWindowsSettings](New-CMTSStepCaptureWindowsSettings)



* [Set-CMTSStepCaptureWindowsSettings](Set-CMTSStepCaptureWindowsSettings)



* [About task sequence steps: Capture Windows Settings](About task sequence steps: Capture Windows Settings)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameCapWinSet = "Capture Windows Settings"
Remove-CMTSStepCaptureWindowsSettings -InputObject $tsOsd -StepName $tsStepNameCapWinSet -Force
```



---


### Parameters
#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a task sequence object from which to remove the Capture Windows Settings step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Capture Windows Settings step to remove from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to remove the Capture Windows Settings step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to remove the Capture Windows Settings step.






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
Remove-CMTSStepCaptureWindowsSettings [-InputObject] <IResultObject> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTSStepCaptureWindowsSettings [-TaskSequenceId] <String> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTSStepCaptureWindowsSettings [-TaskSequenceName] <String> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
