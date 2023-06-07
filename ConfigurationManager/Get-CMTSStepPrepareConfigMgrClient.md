Get-CMTSStepPrepareConfigMgrClient
----------------------------------




### Synopsis
Get the Prepare ConfigMgr Client for Capture step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Prepare ConfigMgr Client for Capture step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepPrepareConfigMgrClient (Remove-CMTSStepPrepareConfigMgrClient.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Prepare ConfigMgr Client for Capture (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_PrepareConfigMgrClientforCapture).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepPrepareConfigMgrClient](New-CMTSStepPrepareConfigMgrClient)



* [Remove-CMTSStepPrepareConfigMgrClient](Remove-CMTSStepPrepareConfigMgrClient)



* [Set-CMTSStepPrepareConfigMgrClient](Set-CMTSStepPrepareConfigMgrClient)



* [About task sequence steps: Prepare ConfigMgr Client for Capture](About task sequence steps: Prepare ConfigMgr Client for Capture)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNamePrepClient = "Prepare ConfigMgr Client for Capture"
$tsStepPrepClient = Get-CMTSStepApplyNetworkSetting -InputObject $tsOsd -StepName $tsStepNamePrepClient
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Prepare ConfigMgr Client for Capture step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Prepare ConfigMgr Client for Capture step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Prepare ConfigMgr Client for Capture step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Prepare ConfigMgr Client for Capture step.






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
Get-CMTSStepPrepareConfigMgrClient [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepPrepareConfigMgrClient [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepPrepareConfigMgrClient [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
