Remove-CMTSStepJoinDomainWorkgroup
----------------------------------




### Synopsis
Remove the Join Domain or Workgroup step from a task sequence.



---


### Description

Use this cmdlet to remove an instance of the Join Domain or Workgroup step from a task sequence.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepJoinDomainWorkgroup](Get-CMTSStepJoinDomainWorkgroup)



* [New-CMTSStepJoinDomainWorkgroup](New-CMTSStepJoinDomainWorkgroup)



* [Set-CMTSStepJoinDomainWorkgroup](Set-CMTSStepJoinDomainWorkgroup)



* [About task sequence steps: Join Domain or Workgroup](About task sequence steps: Join Domain or Workgroup)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsStepNameJoinDomain = "Join Domain or Workgroup"
Remove-CMTSStepJoinDomainWorkgroup -InputObject $tsOsd -StepName $tsStepNameJoinDomain -Force
```



---


### Parameters
#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a task sequence object from which to remove the Join Domain or Workgroup step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **StepName**

Specify the name of the Join Domain or Workgroup step to remove from the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to remove the Join Domain or Workgroup step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence from which to remove the Join Domain or Workgroup step.






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
Remove-CMTSStepJoinDomainWorkgroup [-InputObject] <IResultObject> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTSStepJoinDomainWorkgroup [-TaskSequenceId] <String> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTSStepJoinDomainWorkgroup [-TaskSequenceName] <String> [-Force] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
