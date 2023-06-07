Get-CMTSStepConnectNetworkFolder
--------------------------------




### Synopsis
Get the Connect To Network Folder step from a specific task sequence.



---


### Description

Use this cmdlet to get a task sequence step object for one or more instances of the Connect To Network Folder step. You can use this object to:



- Remove the step from a task sequence with Remove-CMTSStepConnectNetworkFolder (Remove-CMTSStepConnectNetworkFolder.md)- Copy the step to another task sequence with Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md)For more information on this step, see About task sequence steps: Connect To Network Folder (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ConnectToNetworkFolder).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepConnectNetworkFolder](New-CMTSStepConnectNetworkFolder)



* [Remove-CMTSStepConnectNetworkFolder](Remove-CMTSStepConnectNetworkFolder)



* [Set-CMTSStepConnectNetworkFolder](Set-CMTSStepConnectNetworkFolder)



* [About task sequence steps: Connect To Network Folder](About task sequence steps: Connect To Network Folder)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameConnNet = "Connect To Network Folder"
$tsStepConnNet = Get-CMTSStepConnectNetworkFolder -InputObject $tsOsd -StepName $tsStepNameConnNet
```



---


### Parameters
#### **InputObject**

Specify a task sequence object from which to get the Connect To Network Folder step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Connect To Network Folder step to get from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Connect To Network Folder step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to get the Connect To Network Folder step.






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
Get-CMTSStepConnectNetworkFolder [-InputObject] <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepConnectNetworkFolder [-TaskSequenceId] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Get-CMTSStepConnectNetworkFolder [-TaskSequenceName] <String> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
